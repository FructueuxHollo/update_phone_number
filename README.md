# Update Beninese Phone Numbers to Ten-Digit Format

## Context

The Beninese government mandated a change in the format of phone numbers (01/12/2024). All phone numbers must now be ten digits long. This requires adding the prefix `01` after the country code `+229` for all existing eight-digit numbers. For example:

- A number like `+22994******` should be updated to `+2290194******`.

You are managing a dataset of phone numbers with various formats. Some numbers already include the international dialing code `+229`, while others are in local formats or contain multiple numbers separated by delimiters. Updating all these numbers manually would be time-consuming and error-prone.

This Python script automates the process of cleaning and updating the phone numbers in your dataset.

## Purpose

The purpose of this script is to:
1. Standardize all phone numbers in the dataset to start with the international dialing code `+229`.
2. Ensure all phone numbers are updated to the ten-digit format by adding the `01` prefix where needed.
3. Handle multiple phone numbers in a single cell, separated by delimiters like `:::`.
4. Provide an easy-to-use, repeatable solution for processing large datasets of contacts.

## How to Use the Script

### Prerequisites

1. Install Python 3.x on your system.
2. Install the required library:
   ```bash
   pip install -r requirements.txt
   ```
3. Prepare your dataset as a CSV file or a similar format that can be read into a Pandas DataFrame, you can get it through google contacts if you usually synchronise you phone numbers with it.

### Script Overview

The script performs the following steps:

1. **Reads the dataset**: Load your contact dataset into a Pandas DataFrame.
2. **Inspect and updates phone numbers**: Applies a function to update phone numbers to the new ten-digit format.
3. **Handles multiple numbers**: Processes cells with multiple numbers separated by delimiters.
4. **Outputs the updated dataset**: Saves the cleaned and updated dataset to a new file.

### Usage Instructions

1. **Place your dataset**: Ensure your dataset is in a CSV file, with columns containing phone numbers labeled appropriately (e.g., `Phone 1 - Value`, `Phone 2 - Value`, etc.).

2. **Run the script**:
   - Save the script to a Python file, e.g., `update_phone_numbers.py`.
   - Update the `data` variable in the script to point to your dataset or modify the script to read directly from your CSV file.
   - Execute the script:
     ```bash
     python update_phone_numbers.py
     ```

3. **View results**:
   - The script will update all phone numbers and display the updated DataFrame.
   - The script will save the results to a new CSV file called `cleaned_contacts.csv`

### Customization

If your dataset has a different structure or delimiters for multiple numbers, you can modify the following parts of the script:

- **Delimiter handling**: Update the delimiter (`:::`) in the `update_phone_number` function to match your dataset.
- **File reading/writing**: Replace the manual `data` dictionary with file I/O code, such as `pd.read_csv()` and `to_csv()`.

### Limitations

- This script assumes that all valid phone numbers are Beninese and should start with `+229`. If your dataset includes non-Beninese numbers, additional logic may be needed to handle them separately.
- The script does not validate whether a number is functional; it only formats numbers based on the described rules.


