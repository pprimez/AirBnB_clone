# 0x00. AirBnB clone - The console

## 0x00.Table of contents

* [0x01 Introduction](#0x01-Introduction)
* [0x02 Environment](#0x02-Environment)
* [0x03 Installation](#0x03-Installation)
* [0x04 Testing](#0x04-Testing)
* [0x05 Usage](#0x05-Usage)
* [0x06 Authors](#0x06-Authors)

## 0x01 Introduction

Team project to build a clone of [AirBnB](https://www.airbnb.com/).

The console is a command interpreter to manage objects abstraction between objects and how they are stored.

To see the fundamental background of the project visit the [Wiki](https://github.com/ralexrivero/AirBnB_clone/wiki).

The console will perform the following tasks:

* create a new object
* retrive an object from a file
* do operations on objects
* destroy an object

### Storage

All the classes are handled by the `Storage` engine in the `FileStorage` Class.

## 0x02 Environment

<!-- ubuntu -->
<a href="https://ubuntu.com/" target="_blank"> <img height="" src="https://img.shields.io/static/v1?label=&message=Ubuntu&color=E95420&logo=Ubuntu&logoColor=E95420&labelColor=2F333A" alt="Suite CRM"></a> <!-- bash --> <a href="https://www.gnu.org/software/bash/" target="_blank"> <img height="" src="https://img.shields.io/static/v1?label=&message=GNU%20Bash&color=4EAA25&logo=GNU%20Bash&logoColor=4EAA25&labelColor=2F333A" alt="terminal"></a> <!-- python--> <a href="https://www.python.org" target="_blank"> <img height="" src="https://img.shields.io/static/v1?label=&message=Python&color=FFD43B&logo=python&logoColor=3776AB&labelColor=2F333A" alt="python"></a> </a> <!-- vim --> <a href="https://www.vim.org/" target="_blank"> <img height="" src="https://img.shields.io/static/v1?label=&message=Vim&color=019733&logo=Vim&logoColor=019733&labelColor=2F333A" alt="Suite CRM"></a> <!-- vs code --> <a href="https://code.visualstudio.com/" target="_blank"> <img height="" src="https://img.shields.io/static/v1?label=&message=Visual%20Studio%20Code&color=5C2D91&logo=Visual%20Studio%20Code&logoColor=5C2D91&labelColor=2F333A" alt="Suite CRM"></a> </a><!-- git --> <a href="https://git-scm.com/" target="_blank"> <img height="" src="https://img.shields.io/static/v1?label=&message=Git&color=F05032&logo=Git&logoColor=F05032&labelColor=2F333A" alt="git distributed version control system"></a> <!-- github --> <a href="https://github.com" target="_blank"> <img height="" src="https://img.shields.io/static/v1?label=&message=GitHub&color=181717&logo=GitHub&logoColor=f2f2f2&labelColor=2F333A" alt="Github"></a>
 <!-- Style guidelines -->
* Style guidelines:
  * [pycodestyle (version 2.7.*)](https://pypi.org/project/pycodestyle/)
  * [PEP8](https://pep8.org/)

All the development and testing was runned over an operating system Ubuntu 20.04 LTS using programming language Python 3.8.3. The editors used were VIM 8.1.2269, VSCode 1.6.1 and Atom 1.58.0 . Control version using Git 2.25.1.

## 0x03 Installation

```bash
git clone https://github.com/pprimez/AirBnB_clone.git
```

change to the `AirBnb` directory and run the command:

```bash
 ./console.py
```

### Execution

In interactive mode

```bash
$ ./console.py
(hbnb) help

Documented commands (type help <topic>):
========================================
EOF  help  quit

(hbnb)
(hbnb)
(hbnb) quit
$
```

in Non-interactive mode

```bash
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

## 0x04 Testing

All the test are defined in the `tests` folder.

### Documentation

* Modules:

```python
python3 -c 'print(__import__("my_module").__doc__)'
```

* Classes:

```python
python3 -c 'print(__import__("my_module").MyClass.__doc__)'
```

* Functions (inside and outside a class):

```python
python3 -c 'print(__import__("my_module").my_function.__doc__)'
```

and

```python
python3 -c 'print(__import__("my_module").MyClass.my_function.__doc__)'
```

### Python Unit Tests

* unittest module
* File extension ``` .py ```
* Files and folders star with ```test_```
* Organization:for ```models/base.py```, unit tests in: ```tests/test_models/test_base.py```
* Execution command: ```python3 -m unittest discover tests```
* or: ```python3 -m unittest tests/test_models/test_base.py```

### run test in interactive mode

```bash
echo "python3 -m unittest discover tests" | bash
```

### run test in non-interactive mode

To run the tests in non-interactive mode, and discover all the test, you can use the command:

```bash
python3 -m unittest discover tests
```


## 0x05 Usage

* Start the console in interactive mode:

```bash
$ ./console.py
(hbnb)
```

* Use help to see the available commands:

```bash
(hbnb) help

Documented commands (type help <topic>):
========================================
EOF  all  count  create  destroy  help  quit  show  update

(hbnb)
```

* Quit the console:

```bash
(hbnb) quit
$
```

### Commands

> The commands are displayed in the following format *Command / usage / example with output*

* Create

> *Creates a new instance of a given class. The class' ID is printed and the instance is saved to the file file.json.*

```bash
create <class>

```

```bash
(hbnb) create BaseModel
f80e4504-03d0-4575-8588-8f9264edfe09
(hbnb)
```

* Show

```bash
show <class> <id>
```

```bash
(hbnb) show BaseModel f80e4504-03d0-4575-8588-8f9264edfe09
[BaseModel] (f80e4504-03d0-4575-8588-8f9264edfe09) {'id': 'f80e4504-03d0-4575-8588-8f9264edfe09', 'created_at': datetime.datetime(2023, 2, 14, 3, 45, 14, 581541), 'updated_at': datetime.datetime(2023, 2, 14, 3, 45, 14, 581541)}
(hbnb)
```

* Destroy

> *Deletes an instance of a given class with a given ID.*
> *Update the file.json*

```bash
(hbnb) create User
dcf3eb39-6290-4b27-9a3e-3f68cb9c7162
(hbnb) destroy User dcf3eb39-6290-4b27-9a3e-3f68cb9c7162
(hbnb) show User dcf3eb39-6290-4b27-9a3e-3f68cb9c7162
** no instance found **
(hbnb)
```

* all

> *Prints all string representation of all instances of a given class.*
> *If no class is passed, all classes are printed.*

```bash
(hbnb) create BaseModel
40ab5b1d-d221-4dd6-85bc-19a30d41e1b3
(hbnb) all BaseModel
["[BaseModel] (7dbdcc0b-83e7-4cd2-9c3e-591eebc92b28) {'id': '7dbdcc0b-83e7-4cd2-9c3e-591eebc92b28', 'created_at': datetime.datetime(2023, 2, 14, 3, 32, 58, 999967), 'updated_at': datetime.datetime(2023, 2, 14, 3, 32, 59, 683), 'name': 'My First Model', 'my_number': 89}", "[BaseModel] (329669a7-906a-4f2f-8789-1f4d9ed4fe36) {'id': '329669a7-906a-4f2f-8789-1f4d9ed4fe36', 'created_at': datetime.datetime(2023, 2, 14, 3, 39, 25, 88665), 'updated_at': datetime.datetime(2023, 2, 14, 3, 39, 25, 88665)}", "[BaseModel] (9dad50bd-cd12-4a09-a5b5-17c84a536dc9) {'id': '9dad50bd-cd12-4a09-a5b5-17c84a536dc9', 'created_at': datetime.datetime(2023, 2, 14, 3, 43, 26, 371719), 'updated_at': datetime.datetime(2023, 2, 14, 3, 43, 26, 371719)}", "[BaseModel] (f80e4504-03d0-4575-8588-8f9264edfe09) {'id': 'f80e4504-03d0-4575-8588-8f9264edfe09', 'created_at': datetime.datetime(2023, 2, 14, 3, 45, 14, 581541), 'updated_at': datetime.datetime(2023, 2, 14, 3, 45, 14, 581541)}", "[BaseModel] (40ab5b1d-d221-4dd6-85bc-19a30d41e1b3) {'id': '40ab5b1d-d221-4dd6-85bc-19a30d41e1b3', 'created_at': datetime.datetime(2023, 2, 14, 3, 49, 18, 502930), 'updated_at': datetime.datetime(2023, 2, 14, 3, 49, 18, 502930)}"]
(hbnb)
```

* count

> *Prints the number of instances of a given class.*

```bash
(hbnb) create City
8249b0f3-75c8-477c-90c2-c22305116449
(hbnb) create City
6e399ff0-39cc-400d-b91f-6b2f715ed976
(hbnb) count City
2
(hbnb)
```

* update

> *Updates an instance based on the class name, id, and kwargs passed.*
> *Update the file.json*

```bash
(hbnb) create User
fd63fd21-11b7-44fc-aace-26245af61cc5
(hbnb) update User fd63fd21-11b7-44fc-aace-26245af61cc5 email "abrahamoba78@gmail.com"
(hbnb) show User fd63fd21-11b7-44fc-aace-26245af61cc5
[User] (fd63fd21-11b7-44fc-aace-26245af61cc5) {'id': 'fd63fd21-11b7-44fc-aace-26245af61cc5', 'created_at': datetime.datetime(2023, 2, 14, 3, 52, 8, 28799), 'updated_at': datetime.datetime(2023, 2, 14, 3, 52, 8, 28799), 'email': 'abrahamoba78@gmail.com'}
(hbnb)

```
## Authors
<details>
    <summary>Abraham Obayomi</summary>
    <ul>
    <li><a href="https://www.github.com/pprimez">Github</a></li>
    <li><a href="https://www.twitter.com/abrahampraise__">Twitter</a></li>
    <li><a href="mailto:abrahamoba78@gmail.com">e-mail</a></li>
    </ul>
</details>
<details>
    <summary>Aniekeme Umoren</summary>
    <ul>
    <li><a href="https://www.github.com/Kaluu-cpu">Github</a></li>
    <li><a href="https://www.twitter.com/">Twitter</a></li>    
    </ul>
</details>
