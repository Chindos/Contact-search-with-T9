Description
tnine is a C console utility for searching contacts using an algorithm similar to T9 predictive input. The program reads a list of contacts from standard input, where each contact is specified by two strings (name and phone number), and allows you to search by both number and name.

Features

Read contacts:
The program accepts up to 100 contacts as input. Each contact consists of a name and a phone number entered sequentially.

Contact Search:

NORMAL_MODE: The search is performed using the standard findNumber and findText algorithms.
S_MODE: An alternative search mode, activated by the -s flag, using the findNumberS and findTextS functions.
T9 encoding:
The string_map array is used to map numeric keys to letters (e.g., the number 2 corresponds to the string “abc”).

Compilation

bash
Copy
gcc tnine.c -o tnine
Usage

Output all contacts:
If the program is run without arguments, it outputs a list of all read contacts:

bash
Copy
./tnine < contacts.txt
Digit string search:
Pass a numeric string as an argument to the search:

bash
Copy
./tnine 123
S_MODE activation:
To use the alternate search mode, run the program with the -s flag:

bash
Copy
./tnine -s 123
Input data format

Contacts are input as pairs of strings:
The first line is the contact's name.
The second line is the phone number.
Example of contacts.txt file:

diff
Copy
Ivan Ivanov
+123456789
Maria Petrova
+987654321
Algorithm of work

Input decoding:
The decodeString function converts an incoming numeric string into an array of strings corresponding to the letters on the phone keypad.
Finding:
The findNumber and findText functions (and their counterparts in S_MODE) look for matches in a contact's number or name.
Input validation:
The parseUserInput function processes command line arguments and verifies that a valid numeric string has been entered.
Author and contacts

Author: Shynggys Baimukhammedov
Institution: FIT VUT
Date of completion: 18.09.2024
Development time: 19+ hours
