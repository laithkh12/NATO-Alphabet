# 📘 Phonetic Code Generator

This Python program converts a user-input word into its phonetic alphabet equivalent using the NATO phonetic alphabet. It reads data from a CSV file to create a dictionary that maps each letter to its corresponding phonetic code and handles invalid input gracefully

## 📂 Project Structure

- Phonetic Dictionary Creation: Reads from a CSV file containing the NATO phonetic alphabet to create a dictionary.
- Phonetic Code Conversion with Error Handling: Converts a user-input word to its phonetic code using the created dictionary, and re-prompts the user if any non-alphabet characters are entered.
---

## 🔧 Code Explanation

### 1.Phonetic Dictionary Creation
```python
import pandas as pd

data = pd.read_csv("nato_phonetic_alphabet.csv")
phonetic_dict = {row.letter: row.code for (index, row) in data.iterrows()}
print(phonetic_dict)
```
- Reads the NATO phonetic alphabet data from a CSV file and creates a dictionary (phonetic_dict) where each letter is mapped to its phonetic code.
  
### 2.  Phonetic Code Conversion with Error Handling
```python
def generatePhonetic():
    word = input("Enter a word: ").upper()
    try:
        output_list = [phonetic_dict[letter] for letter in word]
    except KeyError:
        print("Only alphabetic characters are allowed. Please try again.")
        generatePhonetic()
    else:
        print(output_list)

generatePhonetic()
```
- Prompts the user for a word, converts it to uppercase, and creates a list of the corresponding phonetic codes.
- If the user enters non-alphabet characters, a KeyError is raised, triggering an error message and a recursive call to generatePhonetic() to re-prompt the user.

## 🚀 How to Run
1. Ensure you have pandas installed
```bash
pip install pandas
```
2. Place the nato_phonetic_alphabet.csv file in the same directory as the script. This file should have two columns labeled letter and code.
3. Run the script
```bash
python script_name.py
```
4. Input any word when prompted, and the program will output the phonetic code equivalent.

## 📝 Notes
- Input Handling: Non-alphabetic characters trigger an error message and re-prompt the user.
- File Structure: nato_phonetic_alphabet.csv should contain columns for letter and code, like:
```bash
letter,code
A,Alpha
B,Bravo
...
```
  
## 🔗 Additional Resources
- Pandas Documentation
- NATO Phonetic Alphabet Reference
