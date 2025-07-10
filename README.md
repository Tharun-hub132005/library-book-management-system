## Project: Simple Library Book Management System
This program allows you to:

* Add new books to the library.

* Remove existing books.

* Issue books to students (sets a due date).

* Return books (calculates fines if returned late).

* View all books and their availability.

* Saves data to a file so it persists between runs.
### How this program demonstrates the concepts:
# 1 Dictionaries:

## data["books"] and data["students"]:
These are the primary data structures. They store information using unique keys (like book_id or student_id) to quickly look up or modify details.

## Adding/Removing:
When you add_book, a new entry is created in data["books"]. When you remove_book, an entry is deleted.

## Accessing data:
data["books"][book_id]["title"] shows how you can chain dictionary lookups to get specific pieces of information.

## Iteration:
The display_books function uses data["books"].items() to loop through all books, showing how to process all entries in a dictionary.

# 2 Date Modules (datetime, timedelta):

# Importing:
from datetime import datetime, timedelta brings in the necessary tools.

# Current Date/Time: 
datetime.now() is used to get the exact moment a book is issued or returned.

# Calculating Future Dates:
timedelta(days=7) is added to datetime.now() to automatically set a due date one week in the future.

# Date Comparison and Subtraction:
In return_book, (return_date - due_date).days calculates the number of days difference, crucial for determining if a book is late.

# Formatting Dates:
strftime("%Y-%m-%d") is used to convert datetime objects into clean, standardized strings for saving in the JSON file. strptime() is used to convert them back from strings to datetime objects.

## 3 Conditionals (if, elif, else):

# Flow Control: The menu() function heavily relies on if/elif/else to decide which function to call based on the user's input (e.g., if the user enters "1", call add_book).

# * Validation:

# if book_id in data["books"]::
Checks if a book already exists (when adding) or if it exists (when removing or issuing).

# if data["books"][book_id]["available"]:: 
Checks if a book can be issued.

# if student_id in data["students"]::
Checks if a student has an active borrowing record.

# if delta_days > 0:: 
Determines if a fine needs to be applied.

# User Feedback:
Conditionals are used to provide appropriate messages to the user (e.g., "Book added successfully" vs. "Book already exists").

## * How to Run the Program:
# Save:
Copy the entire code above and paste it into a file named library_system.py (or any other .py extension).

# Open Terminal/Command Prompt:
Navigate to the directory where you saved the file.

# Run: 
Execute the program using the command:

 * Bash

* python library_system.py
* Interact: Follow the on-screen menu prompts. A file named library_data.json will be created in the same directory to save your data.
