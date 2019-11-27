# Programming Basics questions


## Computer science

### Data structures

#### 1. What is the purpose of a list (array in some programming languages) data structure? Name some methods of it!

The most basic data structure in Python is the sequence. Each element of a sequence is assigned a number - its position or index. The first index is zero, the second index is one, and so forth.

The list is a most versatile datatype available in Python which can be written as a list of comma-separated values (items) between square brackets. Important thing about a list is that items in a list don't need to be of the same type.

Purpose:
- We can use the index operator [] to access an item in a list
- Python allows negative indexing for its sequences
- We can access a range of items in a list by using the slicing operator (colon)
- List are mutable, meaning, their elements can be changed
- We can delete one or more items from a list

Methods:
- append() - Add an element to the end of the list
- extend() - Add all elements of a list to the another list
- insert() - Insert an item at the defined index
- remove() - Removes an item from the list
- pop() - Removes and returns an element at the given index
- clear() - Removes all items from the list
- index() - Returns the index of the first matched item
- count() - Returns the count of number of items passed as an argument
- sort() - Sort items in a list in ascending order
- reverse() - Reverse the order of items in the list
- copy() - Returns a shallow copy of the list

#### 2. What is the difference between a list/array and a set?

A set is an unordered collection of items. Every element is unique (no duplicates) and must be immutable (which cannot be changed).

However, the set itself is mutable. We can add or remove items from it.

Sets can be used to perform mathematical set operations like union, intersection, symmetric difference etc.

A set is created by placing all the items (elements) inside curly braces {}, separated by comma or by using the built-in function set().

The difference between a list and a set:
It can have any number of items and they may be of different types (integer, float, tuple, string etc.). But a set cannot have a mutable element, like list, set or dictionary, as its element.
A list can contain any type of element.

#### 3. What is the purpose and methods of a dictionary/map data structure?

Python dictionary is an unordered collection of items. While other compound data types have only value as an element, a dictionary has a key: value pair.

Dictionaries are optimized to retrieve values when the key is known.

While values can be of any data type and can repeat, keys must be of immutable type (string, number or tuple with immutable elements) and must be unique.

Methods:
- clear() - Remove all items form the dictionary.
- copy() - Return a shallow copy of the dictionary.
- get(key[,d]) - Return the value of key. If key doesnot exit, return d (defaults to None).
- items() - Return a new view of the dictionary's items (key, value).
- keys() - Return a new view of the dictionary's keys.
- pop(key[,d]) - Remove the item with key and return its value or d if key is not found. If d is not provided and key is not found, raises KeyError.
- popitem() - Remove and return an arbitary item (key, value). Raises KeyError if the dictionary is empty.
- setdefault(key[,d]) - If key is in the dictionary, return its value. If not, insert key with a value of d and return d (defaults to None).
- update([other]) - Update the dictionary with the key/value pairs from other, overwriting existing keys.
- values() - Return a new view of the dictionary's values

### Algorithms

#### 1. Fibonacci sequences. Write a method (or pseudo code), that generates the Fibonacci sequences.
        def generate_fibonacci_sequences(number):
            i = 0
            nr1 = 0
            nr2 = 1
            nr3 = 0
            fibonacci_list = []
            while i < number:
                fibonacci_list.append(nr3)
                nr1 = nr2
                nr2 = nr3
                nr3 = nr1 + nr2
                i += 1
            j = 1   
            return fibonacci_list
#### 2. How do you find a max value in a list/array if you can’t use any built-in functions?
        def get_max(list):
            max = list[0]
            i = 1
            while i < len(list):
                if list[i] > max:
                    max = list[i]
                i += 1
            return max
#### 3. How do you find the average of values in a list/array if you can’t use any built-in functions?
        def get_average(list):    
            average = 0
            sum = list[0]
            i = 1
            while i < len(list):
                sum = sum + list[i]
                i += 1
            average = sum / len(list)
            return average
#### What do we call an *in-place* sort?
#### Explain an algorithm which sorts a list!

### Programming paradigms - procedural

#### What is the call stack?
#### What is “Stack overflow”?
#### What are the main parts of a function?

### Programming languages - Python  
#### How do you use a dictionary in Python?
#### What does it mean that an object is immutable in Python?
#### What is conditional expression in Python?
#### What are different types of arguments in Python?
#### What is variable shadowing? (context: variable scope)
#### What can happen if you try to delete/drop/add an item from a List, while you are iterating over it in Python?
#### What is the "golden rule" of variable scoping in Python (context: LEGB)? What is the lifetime of variables?
#### If you need to access the iterator variable after a for loop, how would you do it in Python?
#### What type of elements can a list contain in Python?
#### What is slice operator in Python and how to use?
#### What arithmetic operators (+,*,-,/) can be used on lists in Python? What do they do?
#### What is the purpose of the in and not in membership operators in Python?
#### What does the + operator mean when used with strings in Python?
#### Explain f strings in Python?
#### Name 4 iterable types in Python!
#### What is the difference between list/set/dictionary comprehension and a generator expression in Python?
#### Does the order of the function definitions matter in Python? Why?
#### What does unpacking mean in Python?
#### What happens when you try to assign the result of a function which has no return statement to a variable in Python?

## Software engineering

### Debugging

#### What techniques can you use while debugging a program in Python?
#### What does step over, step into and step out mean while using the debugger?
#### How can you start to debug a program from a certain line using the debugger?

### Version control

#### What are the advantages of using a version control system?
#### What is the difference between the working directory, the staging area and the repository in git?
#### What are remote repositories in git?
#### Why does a merge conflict occur?
#### Through what series of commands could you put a new file into a remote repository connected to your existing local repository?
#### What does it mean atomic commits and descriptive commit messages?
#### What’s the difference between git and GitHub?

## Software design

### Clean code

#### What does clean code mean?
#### What steps do we usually do during a clean code refactoring?

### Error handling

#### What is exception handling?
#### What are the basics of exception handling in Python?
#### In which case should we catch an exception? Why?
#### What can/should we do with an exception in the ‘except’ block?
#### What does the else and finally statement do in a try-except block in Python?

## Software Development Methodologies

#### What is the main goal of a retrospective meeting?

## Programming environment

### Unix

#### What is UNIX and what is Linux?
#### What do we call the shell in Linux?
#### What does root means in a Linux environment?
#### How do you access your personal files in Linux?
#### How can you install an application in Linux?
#### What is package management in Linux, what are repositories?
#### How do you navigate in the filesystem with the command line?
#### What does the following commands do: mkdir, rm, cat, cp, touch?
#### How can you look up what does a command do in Linux if you have no internet connection?
#### What does the following commands do: head, tail, more, less?
#### How do you download a file from internet using the terminal?
