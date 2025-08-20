# Week-4-Assignment-
File Handling and Exception Handling Assignment

# Program for the File Read & Write Challenge

# Step 1: Define file names
original_file = 'original.txt'
modified_file = 'modified.txt'

# Step 2: Read content from the original file and modify it
try:
    with open(original_file, 'r') as file:
        content = file.read()
        modified_content = content.upper()
        print(f"Content read from '{original_file}':\n{content}")
        print("-" * 30)
except FileNotFoundError:
    print(f"Error: The file '{original_file}' was not found.")
    exit()

# Step 3: Write the modified content to a new file
try:
    with open(modified_file, 'w') as file:
        file.write(modified_content)
        print(f"Modified content written to '{modified_file}'.")
except IOError as e:
    print(f"An error occurred while writing to the file: {e}")

# Program for the Error Handling Lab

# Step 1: Ask the user for a filename
filename = input("Please enter the name of the file you want to read: ")

# Step 2: Use a try-except block to handle potential errors
try:
    # Attempt to open and read the file
    with open(filename, 'r') as file:
        content = file.read()
        print("\nFile content:")
        print("=" * 30)
        print(content)
        print("=" * 30)

except FileNotFoundError:
    # This block executes if the file does not exist
    print(f"\nError: The file '{filename}' was not found.")
    print("Please make sure the file name is correct and the file exists in the current directory.")
except IOError as e:
    # This block handles other input/output errors (e.g., permissions issues)
    print(f"\nAn input/output error occurred while trying to read the file: {e}")

finally:
    # The finally block will always execute, regardless of whether an exception occurred or not
    print("\nAttempted to read the file. Program finished.")
