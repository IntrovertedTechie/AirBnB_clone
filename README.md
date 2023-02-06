AirBnB clone - The Console

Welcome

This is part one of the Alx AirBnB clone project. In this project, we have created a command interpreter to manage data without a graphical user interface. Our version of the command interpreter provides the ability to create new objects, retrieve objects from files or databases, perform operations such as counting, updating object attributes, and destroying objects.

Table of Contents

Requirements

Installation

Usage

Commands

Testing

Authors

License

Requirements

Ubuntu 20.04 LTS

PEP8 v2.8.*

Python v3.8.5

Allowed editors: vi, vim, emacs

All your files will end with a new line

The first line of all your files should be exactly #!/usr/bin/python3

A README.md file, at the root of the folder of the project, is mandatory

Your code should use the pycodestyle (version 2.8.*)

All your files must be executable

The length of your files will be tested using wc

All your modules should have a documentation (python3 -c 'print(import("my_module").doc)')

All your classes should have a documentation (python3 -c 'print(import("my_module").MyClass.doc)')

All your functions (inside and outside a class) should have a documentation (python3 -c 'print(import("my_module").my_function.doc)' and python3 -c 'print(import("my_module").MyClass.my_function.doc)')

A documentation is not a simple word, it’s a real sentence explaining what’s the purpose of the module, class or method (the length of it will be verified)

Installation

Clone the repository to your local machine using terminal

Usage

Start the console by running ./console.

Type 'help' to see the available commands

Commands

quit

EOF

create

show

destroy

all

update

count

Methods

All, show, destroy, and update can be used with the following syntax:

Testing

The project has been tested using unittest

All your test files should be inside a folder tests

You have to use the unittest module

All your test files should be python files (extension: .py)

All your test files and folders should start by test_

Your file organization in the tests folder should be the same as your project

e.g., For models/base_model.py, unit tests must be in: tests/test_models/test_base_model.py

e.g., For models/user.py, unit tests must be in: tests/test_models/test_user.py

All your tests should be executed by using this command: python3 -m unittest discover tests

You can also test file by file by using this command: python3 -m unittest tests/test_models/test_base_model.py


<h2>Authors</h2>
<ul>
  <li><a href="https://github.com/adioadebayo">Adio Adebayo</a></li>
  <li><a href="https://github.com/SobgeyeOloju">Sobgeye Oloju</a></li>
</ul>
<h2>License</h2>
<p>AirBnB clone is released under the MIT license. See LICENSE for more details.</p>

