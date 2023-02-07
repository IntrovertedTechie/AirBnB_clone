# AIRBNB Clone Project (HBNB)
![Airbnb logo image](./resources/logo.png)
## About
This project is a clone of Airbnb, a platform used to connect people who want to rent homes. It was built as part of a learning effort at Holberton School.
## Console
The console can be used to manipulate and manage app data as demonstrated below:
#### Interactive mode:
```
$ ./console.py
(hbnb) help

<<<<<<< HEAD
Documented commands (type help <topic>):
========================================
EOF  help  quit

(hbnb)
(hbnb)
(hbnb) quit
$
```
#### Non-Interactive mode:
```
$ echo "help" | ./console.py
(hbnb)

Documented commands (type help <topic>):
========================================
EOF  help  quit
(hbnb)
$
$ cat test_help
help
$
$ cat test_help | ./console.py
(hbnb)

Documented commands (type help <topic>):
========================================
EOF  help  quit
(hbnb)
$
```
### Console commands
| Command | Description                                                                    |
| ------- | ------------------------------------------------------------------------------ |
| quit    | Exits console when entered before `EOF` character                              |
| help    | Shows description of all working console commands                              |
| create  | Creates a new instance of the class whose name it precedes                     |
| show    | Prints a string representation of an instance based on the class name and `id` |
| destroy | Deletes an instance based on the class name and `id`                           |
| all     | Prints all string representation of all instances based or not on the classname|
| update  | Updates an instance based on the class name and id by adding/updating attribute|
## Console Shorthand
The console also uses a regex engine to allow you interact with it using shorthand.
### Format:
```
<Class Name>.<command>(<id>, parameters...)
```
Examples:
#### Displays all existing objects with type `User`
```
guillaume@ubuntu:~/AirBnB$ ./console.py
(hbnb) User.all()
[[User] (246c227a-d5c1-403d-9bc7-6a47bb9f0f68) {'first_name': 'Taiwo', 'last_name': 'Orolu', 'created_at': datetime.datetime(2023, 1, 28, 21, 12, 19, 611352), 'updated_at': datetime.datetime(2023, 9, 28, 21, 12, 19, 611363), 'password': '63a9f0ea7bb98050796b649e85481845', 'email': 'taiyeo@mail.com', 'id': '246c227a-d5c1-403d-9bc7-6a47bb9f0f68'}, [User] (38f22813-2753-4d42-b37c-57a17f1e4f88) {'first_name': 'Betty', 'last_name': 'Bar', 'created_at': datetime.datetime(2017, 9, 28, 21, 11, 42, 848279), 'updated_at': datetime.datetime(2017, 9, 28, 21, 11, 42, 848291), 'password': 'b9be11166d72e9e3ae7fd407165e4bd2', 'email': 'airbnb@mail.com', 'id': '38f22813-2753-4d42-b37c-57a17f1e4f88'}]
(hbnb) 
```
#### Number of existing objects with type `User`
```
guillaume@ubuntu:~/AirBnB$ ./console.py
(hbnb) User.count()
2
(hbnb)
```
#### Displays object with type `User`, and `id` equals "246c227a-d5c1-403d-9bc7-6a47bb9f0f68"
```
guillaume@ubuntu:~/AirBnB$ ./console.py
(hbnb) User.show("246c227a-d5c1-403d-9bc7-6a47bb9f0f68")
[User] (246c227a-d5c1-403d-9bc7-6a47bb9f0f68) {'first_name': 'Betty', 'last_name': 'Bar', 'created_at': datetime.datetime(2017, 9, 28, 21, 12, 19, 611352), 'updated_at': datetime.datetime(2017, 9, 28, 21, 12, 19, 611363), 'password': '63a9f0ea7bb98050796b649e85481845', 'email': 'airbnb@mail.com', 'id': '246c227a-d5c1-403d-9bc7-6a47bb9f0f68'}
(hbnb) User.show("Bar")
** no instance found **
(hbnb) 
```
#### Deletes object with type `User`, and `id` equals "246c227a-d5c1-403d-9bc7-6a47bb9f0f68"
```
guillaume@ubuntu:~/AirBnB$ ./console.py
(hbnb) User.count()
2
(hbnb) User.destroy("246c227a-d5c1-403d-9bc7-6a47bb9f0f68")
(hbnb) User.count()
1
(hbnb) User.destroy("Bar")
** no instance found **
(hbnb) 
```
#### Updates object with type `User`, and `id` equals "38f22813-2753-4d42-b37c-57a17f1e4f88"
```
guillaume@ubuntu:~/AirBnB$ ./console.py
(hbnb) User.show("38f22813-2753-4d42-b37c-57a17f1e4f88")
[User] (38f22813-2753-4d42-b37c-57a17f1e4f88) {'first_name': 'Betty', 'last_name': 'Bar', 'created_at': datetime.datetime(2017, 9, 28, 21, 11, 42, 848279), 'updated_at': datetime.datetime(2017, 9, 28, 21, 11, 42, 848291), 'password': 'b9be11166d72e9e3ae7fd407165e4bd2', 'email': 'airbnb@mail.com', 'id': '38f22813-2753-4d42-b37c-57a17f1e4f88'}
(hbnb)
(hbnb) User.update("38f22813-2753-4d42-b37c-57a17f1e4f88", "first_name", "John")
(hbnb) User.update("38f22813-2753-4d42-b37c-57a17f1e4f88", "age", 89)
(hbnb)
(hbnb) User.show("38f22813-2753-4d42-b37c-57a17f1e4f88")
[User] (38f22813-2753-4d42-b37c-57a17f1e4f88) {'age': 89, 'first_name': 'John', 'last_name': 'Bar', 'created_at': datetime.datetime(2017, 9, 28, 21, 11, 42, 848279), 'updated_at': datetime.datetime(2017, 9, 28, 21, 15, 32, 299055), 'password': 'b9be11166d72e9e3ae7fd407165e4bd2', 'email': 'airbnb@mail.com', 'id': '38f22813-2753-4d42-b37c-57a17f1e4f88'}
(hbnb) 
```
#### Updates object with type `User`, and `id` equals "38f22813-2753-4d42-b37c-57a17f1e4f88" with data in the dictionary
Format:
`<class name>.update(<id>, <dictionary representation>)`
```
(hbnb) User.show("38f22813-2753-4d42-b37c-57a17f1e4f88")
[User] (38f22813-2753-4d42-b37c-57a17f1e4f88) {'age': 23, 'first_name': 'Bob', 'last_name': 'Bar', 'created_at': datetime.datetime(2017, 9, 28, 21, 11, 42, 848279), 'updated_at': datetime.datetime(2017, 9, 28, 21, 15, 32, 299055), 'password': 'b9be11166d72e9e3ae7fd407165e4bd2', 'email': 'airbnb@mail.com', 'id': '38f22813-2753-4d42-b37c-57a17f1e4f88'}
(hbnb) 
(hbnb) User.update("38f22813-2753-4d42-b37c-57a17f1e4f88", {'first_name': "John", "age": 89})
(hbnb) 
(hbnb) User.show("38f22813-2753-4d42-b37c-57a17f1e4f88")
[User] (38f22813-2753-4d42-b37c-57a17f1e4f88) {'age': 89, 'first_name': 'John', 'last_name': 'Bar', 'created_at': datetime.datetime(2017, 9, 28, 21, 11, 42, 848279), 'updated_at': datetime.datetime(2017, 9, 28, 21, 17, 10, 788143), 'password': 'b9be11166d72e9e3ae7fd407165e4bd2', 'email': 'airbnb@mail.com', 'id': '38f22813-2753-4d42-b37c-57a17f1e4f88'}
(hbnb) 
```
## Project Structure
![Data diagram](./resources/structure.png)
=======
<h1>AirBnB clone - The Console</h1> <h2>Welcome</h2> <p>This is part one of the Alx AirBnB clone project. In this project, we have created a command interpreter to manage data without a graphical user interface. Our version of the command interpreter provides the ability to create new objects, retrieve objects from files or databases, perform operations such as counting, updating object attributes and destroying objects.</p> <h2>Table of Contents</h2> <ul> <li>Requirements</li> <li>Installation</li>

 <li>Usage</li> <li>Commands</li> <li>Testing</li> <li>Authors</li> <li>License</li> </ul> <h2>Requirements</h2> <ul> <li>Ubuntu 20.04 LTS</li> <li>Python 3.8.5</li> <li>pycodestyle 2.8.* </li> </ul> <h2>Installation</h2> <p>Clone the repository to your local machine using terminal</p> 
<pre>
  <code>
$ git clone https://github.com/AirBnB_clone.git
  </code>
</pre>
 <h2>Usage</h2> 
<pre>
<code>$ ./console</code>
</pre>
<p>Start the console by running ./console. Type 'help' to see the available commands</p>
<pre>
<code>$ help </code>
</pre>
 <h2>Commands</h2> <ul> <li>quit</li> <li>EOF</li> <li>create</li> <li>show</li> <li>destroy</li> <li>all</li> <li>update</li> <li>count</li> </ul> <h2>Methods</h2> <p>All, show, destroy, and update can be used with the following syntax:</p> <h2>Testing</h2> <p>The project has been tested using unittest in the AirBnB_clone/tests directory</p> <h2>Authors</h2> <ul> 
<li><a href="https://github.com/introvertedtechie">Adio Adebayo
</a></li> <li><a href="https://github.com/soclassique">Sobgeye Oloju</a></li> </ul> <h2>License</h2> <p>AirBnB clone is released under the MIT license. See LICENSE for more details.</p>
>>>>>>> 2261fc47c9118ae70e6d605b21e2df8387ae03c2
