# software_engineering_and_devops
Configure a Continuous Integration (CI) pipeline that automates the building and testing of a Python project whenever changes are detected in the remote repository.
Tasks

1.	EC2 Setup
o	Deploy an AWS EC2 instance (t2.large, 8GB volume, Ubuntu OS).
o	Open ports 8080 and 9000.
o	Install Python, Git, and Jenkins.

3.	Git Configuration
o	Configure Git on your instance.
o	Create a remote GitHub/GitLab repository.
o	Push the provided Dex2Hex.py file and confirm it is visible both locally and remotely.

3.	Jenkins Freestyle Project
o	Configure Jenkins to:
a) Detect changes in the remote repository.
b) Compile the code.
c) Run the code with sample input values.

4.	Static Code Analysis
o	Integrate SonarQube and SonarScanner into the Jenkins pipeline to perform static code analysis.
8.	Improve the Python Project
o	Add error handling so that:
	The program returns an error if no input is provided.
	Non-integer inputs are handled gracefully without crashing.
o	Use version control appropriately to track all changes.

5.	Pipeline Testing & Quality Improvements
o	Update the Python project until all tests pass successfully in the CI pipeline.
o	Address feedback provided by SonarQube.
o	Use version control to document the development process.

Practical Code:

import sys
def decimal_to_hex(decimal_value):
 hex_chars = ['0', '1', '2', '3', '4', '5', '6', '7', '8', '9', 'A', 'B', 'C', 'D', 'E',
'F']
 hexadecimal = ""
 num = decimal_value

 print(f"Converting the Decimal Value {num} to Hex...")

 while num != 0:
 rem = num % 16
 hexadecimal = hex_chars[rem] + hexadecimal
 num //= 16

 print(f"Hexadecimal representation is: {hexadecimal}")
 return hexadecimal # Return the hexadecimal value for testing
if __name__ == "__main__":
 if len(sys.argv) > 1:
 try:
 decimal_value = int(sys.argv[1])
 decimal_to_hex(decimal_value)
 except ValueError:
 print("Please provide a valid integer.")
 else:
 print("Usage: python script.py <decimal_number>")

