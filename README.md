# 📘 Phonetic Code Generator

This Python program uses dictionary and data frame manipulation techniques to convert a user-input word into its phonetic alphabet equivalent, based on the NATO phonetic alphabet.

## 📂 Project Structure

- **Student Dictionary**: A simple dictionary of students and scores, with examples of dictionary iteration.
- **DataFrame Iteration**: Demonstrates iterating through a pandas DataFrame, with student data as an example.
- **Phonetic Code Conversion**: The core functionality, which creates a phonetic dictionary from a CSV file and then converts a user-input word to the corresponding phonetic alphabet.

---

## 🔧 Code Explanation

### 1. Dictionary Iteration Example
```python
student_dict = {
    "student": ["Angela", "James", "Lily"], 
    "score": [56, 76, 98]
}

# Looping through dictionaries
for (key, value) in student_dict.items():
    # Access key and value
    pass
```
- This section demonstrates how to iterate over a dictionary to access keys and values.

### 2. DataFrame Iteration Example
```python
import pandas as pd

student_data_frame = pd.DataFrame(student_dict)

# Loop through rows of a DataFrame
for (index, row) in student_data_frame.iterrows():
    # Access index and row
    # Access row.student or row.score
    pass
```
- Converts student_dict to a pandas DataFrame, then iterates through it using iterrows() to access each row's data.

### 3. Phonetic Code Conversion
```python
import pandas as pd

data = pd.read_csv("nato_phonetic_alphabet.csv")
phoneticDict = {row.letter: row.code for (index, row) in data.iterrows()}

word = input("Enter a word: ").upper()
outputList = [phoneticDict[letter] for letter in word]
```
- Step 1: Creates a dictionary called phoneticDict using dictionary comprehension from a CSV file.
- Step 2: Prompts the user for a word and generates a list, outputList, containing the phonetic alphabet codes.


## 🚀 How to Run
1. Ensure you have pandas installed
```bash
pip install pandas
```
2. Place the nato_phonetic_alphabet.csv file in the same directory as the script.
3. Run the script
```bash
python script_name.py
```
4. Input any word when prompted to see the phonetic code.

## 📝 Notes
- Input Handling: The word is converted to uppercase to match the phonetic dictionary keys.
- CSV Format: The nato_phonetic_alphabet.csv file should contain columns named letter and code.

## 🔗 Additional Resources
- Pandas Documentation
- NATO Phonetic Alphabet Reference
