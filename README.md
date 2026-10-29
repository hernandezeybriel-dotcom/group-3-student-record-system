# STUDENT RECORD SYSTEM
Project Overview
Student Record Management System is a console-based C++ application that stores and manages student records using a singly linked list, with file-based persistence.

# PURPOSE
The system allows users to create, view, delete, and sort student records (ID, Name, Course, GPA) while keeping the data saved between sessions in a text file.

# HOW IT WORKS

Startup: The program reads students.txt and loads every valid record into the linked list. Invalid or corrupted lines are skipped.
Menu loop: The user chooses from six options: Add, Display, Delete, Sort by GPA, Save, and Exit.
Action: The selected operation runs on the in-memory linked list, and the program returns to the menu.
Shutdown: On exit, all records are written back to students.txt, and the class destructor releases every allocated node.

# CORE DATA STRUCTURE AND ALGORITHMS
Singly linked list: Each node stores a student's data and a pointer to the next node, which allows the list to grow and shrink dynamically.
Insertion: A new node is appended to the end of the list.
Deletion (node bypass): The preceding node is relinked to skip the target node, which is then freed.
Sorting: Records are ordered by GPA, with the best grade (1.00) first.
File I/O: Records are stored one per line using a | delimiter and read back on startup.

# DESIGN AND QUALITY
Object-oriented design: All list operations are encapsulated in the StudentList class, and its destructor guarantees that no memory is leaked.
Input validation: IDs must be positive and unique, GPA must fall between 1.00 and 5.00 (rejecting values such as nan), and text fields cannot be blank or contain the delimiter.
Robustness: Corrupted file entries are ignored, file errors are reported, and the program exits cleanly if input ends unexpectedly instead of looping forever.

Summary
The system combines a dynamic linked list for efficient in-memory management with file storage for persistence, while input validation and automatic memory cleanup keep the program secure and reliable.
