# Python - AirBnB   :dart:

### Creation of a command interpreter in Python using the cmd module, in order to manage the Back-End part
## **What's a command interpreter?**
It is an environment that allows us to manage the different objects involved in the project. 
It allows to:

**`- `** Create a new object.
Ex: A new user; a new place...

**`- `** Recover an object in a file, a database etc...

**`- `** Perform operations on objects: Counting, calculating statistics, etc...

**`- `** Update object attributes

**`- `** Delete an object(...)

## A macro view of the flow of a run from console command

![SERVER SIDE: BACK-END](/AirBnB/Pictures/Back-End3.png)


`In order to answer this main question (What's a command interpreter?), 
we will have to break it down into several small parts, through several other questions (below) which will allow us to deal with the subject more effectively.
`

**This will also allow through the definition of each Object, to discover how the program works**

### The purpose of using the console is to have an environment for managing the various object events, more or less automated.
### We have within this framework 5 main groups of objects:

 **`I. `** *Set up a parent class. Here: BaseModel. It allows to manage the initializations*

**`II. `**  *Create a simple Serialization/Deserialization stream*

**`III. `** *Create all the classes used in the project: User,State, City, Place... 
             which inherits from the BaseModel parent class*

**`IV. `** *Create an abstract storage engine from the project: File Storage*

**`V. `**  *Create all class and storage engine validation tests*
#

## `The main interactive components`
### **`A - `** **Class BaseModel`**

BaseModel is a class thas has three attributes: `id`, `created_at`, and `updated_at`. 
The `id attribute` is a `unique identifier` generated using the `uuid module`. 
The `created_at` and `updated_at` attributes are `datetime objects` that represent the 
date and time when the instance was created and last updated.
	
The __str__ method returns a string that represents the instance, including the `class name`, 
the `id attribute`, and the __dict__ attribute.

The `save method` updates the `updated_at` attribute with the current date and time.

The `to_dict method` returns a dictionary that contains all the attributes of the instance, 
including the __class__ attribute, the `id attribute`, the `created_at` attribute, and the 
`updated_at` attribute. The `created_at` and `updated_at` attributes are formatted as ISO 8601 strings.

### **`B - `** **Class User and Others**
These are the classes that inherited from the mother class, BaseModel

### **`C - `** **Class FileStore**
This is the class that will allow objects to be saved in their states, for future use. This class also makes it possible to manage serialization and deserialization for the purpose of a future opening of flows to the Front-End
#

## Definition of importants terms used

*  What is a **`Python package`**: 
*  What is a **`command interpreter`** in Python using the cmd module
*  What is **`Unit testing`** and how to implement it in a large project
*  What is the **`serialize`** and **`deserialize`** a Class
*  How to write and read a **`JSON file`**
*  What is **`datetime`**
*  What is an **`UUID`**
*  What is **`*args`** and how to use it
*  What is **`**kwargs`** and how to use it
*  How to **`handle named arguments in a function`**

1. ### `Python Package`: 
   The simplest definition of a Package is a folder that contains Modules.
   in other words, it's a collection of related Python modules organized in a directory hierarchy. 
   A package can contain modules, other packages, data, configuration files and miscellaneous resources
    
2. ### `Unit test`:
   Unit tests (or unit tests) are automated tests that verify the proper functioning of a function, 
   a method or an isolated module independently.

   **All tests should also pass in non-interactive mode: `$ echo "python3 -m unittest discover tests" | bash`**

3. ### `Serialize and Deserialize`:
   The Serialization is the process throught what, we convert the python object to JSON formt; 
   
   And the Deserialization is in the other sens, the convertion of the JASON format back to python object.
   
4. ### `Write JSON file` / ` Read JSON file`:
```
Example:

import json

"""creat a ditionnary"""
data = {"nom": "example1", "prenom": "example2"}

"""Open a file in write mode"""
with open("fichier.json", "w") as f:

"""Write JSON data to file"""
   json.dump(data, f)

``` 
   
5. ### `Datetime`:
   This module provides methods for manipulating dates and times:

  |Modules  | Some Methodes|
  |--------:|:-------------|
  |Calendar |  now()       |
  |time     |  isoformat() |
  |Zoneinfo |  strftime()  |
  |dateutil |     ...      |
   

6. ### `UUID`: 
   Is the Universally Unique Identifier. A Python Module that allows to produce different uuid version, 
   based on the timestamp
   
7. ### `*args` / `**Kwargs`:
   *args and **kwargs allow you to pass a variable number of arguments to a function.

   **-** *args is used to send a non-keyworded variable length argument list to the function.

   **-** **kwargs allows you to pass keyworded variable length of arguments to a function. 
           You should use **kwargs if you want to handle named arguments in a function.
#
## `A broader view of the Back-End with the different Objects`

![SERVER SIDE: BACK-END](/AirBnB/Pictures/Vue_generale_cmd.png)

#

### **`D - `** **How to Start it**
The program starts when the **`console.py`** file is executed as we can see in this example below:
![START CMD](/AirBnB/Pictures/Start_Console.png)
### **`E - `** **One of possible Use Case of the Console**
Let's see what happens when you want to create a new object using the **`creat`** command, Example: **`creat`** _BaseModel2_
![USE CASE](/AirBnB/Pictures/Cmd_flow.png)

#

## `Commandes `     :floppy_disk:

|   conditions  |     loops    | Instructions|   Modules|
| ------------- |:------------:|:-----------:|:--------:|
|      if       |    while     |    break    |   Dir()  |
|     else      |     for      |    pass     | filter   |
|     elif      |     lambda   |  continues  | reduce   |
|      random   |    import    |      map    |   os     |
|     pathlib   |    finally   |    del      |   raise  |
|    assert     |    from      |    yield    |   in     | 
|     pass      |      is      |     global  |   local  |
|     except    |     break    |     or      |    and   |
|     def       |     try      |     class   |   for    |


#
## ` Python Unit Tests `

* Allowed editors: vi, vim, emacs
* All your files should end with a new line
* All your test files should be inside a folder tests
* You have to use the unittest module
* All your test files should be python files (extension: .py)
* All your test files and folders should start by test_
* Your file organization in the tests folder should be the same as your projecte.g., 
  For models/base_model.py, unit tests must be in: tests/test_models/test_base_model.py
* e.g., For models/user.py, unit tests must be in: tests/test_models/test_user.py
* All your tests should be executed by using this command: python3 -m unittest discover tests
* You can also test file by file by using this command: python3 -m unittest tests/test_models/test_base_model.py
* All your modules should have a documentation (python3 -c `'print(__import__("my_module").__doc__)')`
* All your classes should have a documentation (python3 -c `'print(__import__("my_module").MyClass.__doc__)')`
* All your functions (inside and outside a class) should have a documentation (python3 -c 
* `'print(__import__("my_module").my_function.__doc__)'` and python3 -c `'print(__import__("my_module").MyClass.my_function.__doc__)'`
* We strongly encourage you to work together on test cases, 
* so that you don’t miss any edge case

 #

## `Resources `   :earth_africa:

### [Python packages](https://intranet.hbtn.io/concepts/66).
### [AirBnB clone](https://intranet.hbtn.io/concepts/74).
### [cmd module](https://intranet.hbtn.io/rltoken/_mUwX-Mn69bDBP5iTQmCJA).
### [uuid module](https://intranet.hbtn.io/rltoken/4HNpF8nsTMociNaTgMYAeQ).
### [datetime](https://intranet.hbtn.io/rltoken/xnmMG0Qin2K9CxXdmQoZkA).
### [unittest module](https://intranet.hbtn.io/rltoken/MKNUT1FRSdUiGIpwMmrtgw).
### [args/kwargs](https://intranet.hbtn.io/rltoken/mY-8n8I-ohQIjkUOqcK6Rw).
### [Python test cheatsheet](https://intranet.hbtn.io/rltoken/9PsyQoeiVNhWGcj_1PkZJg).


## :spider_web: :fist_raised:
