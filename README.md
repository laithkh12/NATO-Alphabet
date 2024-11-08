# 📘 Phonetic Code Generator

This Python program takes a user-input word and converts it to its phonetic alphabet equivalent using the NATO phonetic alphabet. It reads data from a CSV file to create a dictionary mapping each letter to its corresponding phonetic code.

## 📂 Project Structure

- Phonetic Dictionary Creation: Reads from a CSV file containing the NATO phonetic alphabet to create a dictionary.
- Phonetic Code Conversion: Converts a user-input word to its phonetic code using the created dictionary.

---

## 🔧 Code Explanation

### 1.Phonetic Dictionary Creation
```python
import pandas as pd

data = pd.read_csv("nato_phonetic_alphabet.csv")
phonetic_dict = {row.letter: row.code for (index, row) in data.iterrows()}
print(phonetic_dict)
```
- This section reads the NATO phonetic alphabet data from a CSV file and uses dictionary comprehension to create a dictionary (phonetic_dict) where each letter is mapped to its phonetic code.

### 2. Phonetic Code Conversion
```python
word = input("Enter a word: ").upper()
output_list = [phonetic_dict[letter] for letter in word]
print(output_list)
```
- After creating the phonetic dictionary, the program prompts the user for a word, converts it to uppercase, and generates a list (output_list) of the corresponding phonetic alphabet codes.

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
- Case Handling: The input word is converted to uppercase to ensure matching with the dictionary keys.
  
## 🔗 Additional Resources
- Pandas Documentation
- NATO Phonetic Alphabet Reference
