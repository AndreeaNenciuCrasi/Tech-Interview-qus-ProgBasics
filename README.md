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

#### 4. What do we call an *in-place* sort?

You can also use the list.sort() method of a list. It modifies the list in-place (and returns None to avoid confusion). Usually it's less convenient than sorted() - but if you don't need the original list, it's slightly more efficient.

        >>> a = [5, 2, 3, 1, 4]
        >>> a.sort()
        >>> a
        [1, 2, 3, 4, 5]

Another difference is that the list.sort() method is only defined for lists. In contrast, the sorted()function accepts any iterable.

        >>> sorted({1: 'D', 2: 'B', 3: 'B', 4: 'E', 5: 'A'})
        [1, 2, 3, 4, 5]

#### 5. Explain an algorithm which sorts a list!

Bubble Sort is the simplest sorting algorithm that works by repeatedly swapping the adjacent elements if they are in wrong order.

        def bubbleSort(arr):
            n = len(arr)
        
            # Traverse through all array elements
            for i in range(n):
        
                # Last i elements are already in place
                for j in range(0, n-i-1):
        
                    # traverse the array from 0 to n-i-1
                    # Swap if the element found is greater
                    # than the next element
                    if arr[j] > arr[j+1] :
                        arr[j], arr[j+1] = arr[j+1], arr[j]

### Programming paradigms - procedural

#### 1. What is the call stack?

Python stores information about functions which have been called in a call stack. Whenever a function is called, a new stack frame is added to the stack – all of the function’s parameters are added to it, and as the body of the function is executed, local variables will be created there. When the function finishes executing, its stack frame is discarded, and the flow of control returns to wherever you were before you called the function, at the previous level of the stack.


#### 2. What is “Stack overflow”?

Python’s stack has a finite size – if we keep placing instances of the function on the stack(recursion) we will eventually fill it up and cause a stack overflow. Python protects itself from stack overflows by setting a limit on the number of times that a function is allowed to recurse.

#### 3. What are the main parts of a function?

        def NAME( LIST OF PARAMETERS ):
            STATEMENTS

There can be any number of statements inside the function, but they have to be indented from the def. 

Function definitions:
- A header, which begins with a keyword and ends with a colon.
- A body consisting of one or more Python statements, each indented the same amount – 4 spaces is the Python standard – from the header.



### Programming languages - Python

#### 1. How do you use a dictionary in Python?

The Python dictionary type is called dict. We can use a dictionary to store key-value pairs. To define a dictionary literal, we put a comma-separated list of key-value pairs between curly brackets. We use a colon to separate each key from its value. We access values in the dictionary in much the same way as list or tuple elements, but we use keys instead of indices:

        marbles = {"red": 34, "green": 30, "brown": 31, "yellow": 29 }

        personal_details = {
            "name": "Jane Doe",
            "age": 38, # trailing comma is legal
        }

        print(marbles["green"])
        print(personal_details["name"])

        # modify a value
        marbles["red"] += 3
        personal_details["name"] = "Jane Q. Doe"

The keys of a dictionary don’t have to be strings – they can be any immutable type, including numbers and even tuples. We can mix different types of keys and different types of values in one dictionary. Keys are unique – if we repeat a key, we will overwrite the old value with the new value. When we store a value in a dictionary, the key doesn’t have to exist – it will be created automatically:

        battleship_guesses = {
            (3, 4): False,
            (2, 6): True,
            (2, 5): True,
        }

        surnames = {} # this is an empty dictionary
        surnames["John"] = "Smith"
        surnames["John"] = "Doe"
        print(surnames) # we overwrote the older surname

        marbles = {"red": 34, "green": 30, "brown": 31, "yellow": 29 }
        marbles["blue"] = 30

Like sets, dictionaries are not ordered – if we print a dictionary, the order will be random.

Here are some commonly used methods of dictionary objects:

        marbles = {"red": 34, "green": 30, "brown": 31, "yellow": 29 }

        # Get a value by its key, or None if it doesn't exist
        marbles.get("orange")
        # We can specify a different default
        marbles.get("orange", 0)

        # Add several items to the dictionary at once
        marbles.update({"orange": 34, "blue": 23, "purple": 36})

        # All the keys in the dictionary
        marbles.keys()
        # All the values in the dictionary
        marbles.values()
        # All the items in the dictionary
        marbles.items()

We can check if a key is in the dictionary using in and not in:

        print("purple" in marbles)
        print("white" not in marbles)
        
We can also check if a value is in the dictionary using in in conjunction with the values method:

    print("Smith" in surnames.values())

#### 2. What does it mean that an object is immutable in Python?

A mutable(list, dictionary, set) object can be changed after it is created, and an immutable object can’t.
Objects of built-in types like (int, float, bool, str, tuple, unicode) are immutable.

- Python handles mutable and immutable objects differently.
- Immutable are quicker to access than mutable objects.
- Mutable objects are great to use when you need to change the size of the object, example list, dict etc.. Immutables are used when you need to ensure that the object you made will always stay the same.
- Immutable objects are fundamentally expensive to “change”, because doing so involves creating a copy. Changing mutable objects is cheap.

#### 3. What is conditional expression in Python?

Python supports one additional decision-making entity called a conditional expression. (It is also referred to as a conditional operator or ternary operator in various places in the Python documentation.) 

In its simplest form, the syntax of the conditional expression is as follows:

        <expr1> if <conditional_expr> else <expr2>

This is different from the if statement forms listed above because it is not a control structure that directs the flow of program execution. It acts more like an operator that defines an expression. In the above example, <conditional_expr> is evaluated first. If it is true, the expression evaluates to <expr1>. If it is false, the expression evaluates to <expr2>.

Notice the non-obvious order: the middle expression is evaluated first, and based on that result, one of the expressions on the ends is returned. Here are some examples that will hopefully help clarify:

        >>> raining = False
        >>> print("Let's go to the", 'beach' if not raining else 'library')
        Let's go to the beach
        >>> raining = True
        >>> print("Let's go to the", 'beach' if not raining else 'library')
        Let's go to the library

        >>> age = 12
        >>> s = 'minor' if age < 21 else 'adult'
        >>> s
        'minor'

        >>> 'yes' if ('qux' in ['foo', 'bar', 'baz']) else 'no'
        'no'

#### 4. What are different types of arguments in Python?

Types of Python Function Arguments


a. Default Argument in Python
Python Program arguments can have default values. We assign a default value to an argument using the assignment operator in python(=). When we call a function without a value for an argument, its default value (as mentioned) is used.

        >>> def greeting(name='User'):
                        print(f"Hello, {name}")
        >>> greeting('Ayushi')

Any number of arguments can have a default value. But you must make sure to not have a non-default argument after a default argument. In other words, if you provide a default argument, all others succeeding it must have default values as well. The reason is simple. Imagine you have a function with two parameters. The first argument has a default value, but the second doesn’t. Now when you call it(if it was allowed), you provide only one argument. The interpreter takes it to be the first argument. What happens to the second argument, then? It has no clue.


b. Python Keyword Arguments
With keyword arguments in python, we can change the order of passing the arguments without any consequences. Let’s take a function to divide two numbers, and return the quotient.

        >>> def divide(a,b):
                        return a/b
        >>> divide(3,2)

We can call this function with arguments in any order, as long as we specify which value goes into what.

        >>> divide(a=1,b=2)
        0.5

        >>> divide(b=2,a=1)
        0.5
As you can see, both give us the same thing. These are keyword python function arguments.
But if you try to put a positional argument after a keyword argument, it will throw Python exception of SyntaxError.

        >>> divide(b=2,1)
SyntaxError: positional argument follows keyword argument in python.


c. Python Arbitrary Arguments
You may not always know how many arguments you’ll get. In that case, you use an asterisk(*) before an argument name.

        >>> def sayhello(*names):
                        for name in names:
                                        print(f"Hello, {name}")
And then when you call the function with a number of arguments, they get wrapped into a Python tuple. We iterate over them using the for loop in python.

        >>> sayhello('Ayushi','Leo','Megha')
        Hello, Ayushi
        Hello, Leo
        Hello, Megha

#### 5. What is variable shadowing? (context: variable scope)

In computer programming, variable shadowing occurs when a variable declared within a certain scope (decision block, method, or inner class) has the same name as a variable declared in an outer scope. At the level of identifiers (names, rather than variables), this is known as name masking. This outer variable is said to be shadowed by the inner variable, while the inner identifier is said to mask the outer identifier. This can lead to confusion, as it may be unclear which variable subsequent uses of the shadowed variable name refer to, which depends on the name resolution rules of the language.

#### 6. What can happen if you try to delete/drop/add an item from a List, while you are iterating over it in Python?

As we know, every item in a list lives at its own unique index; which are in order, starting from 0. If we remove an item, any item with an index greater than the one we've removed has now been shifted down.

And here's why that matters:

        foo = ['a', 'b', 'c', 'd']
        for index in range(len(foo)):
            del foo[index]

In this loop, we're removing all the elements, so we should end up with foo == [], right? This is not the case. In our first trip through the loop, we remove the item at index 0, and the item at index 1 becomes the item at index 0. Our next time through the loop, we remove the item at index 1 which was previously the item at index 2.

In just the first two iterations, we've removed 'a' and 'c' from the array, *but we've neglected to remove 'b'. Once we get to the third iteration (where we though we'd remove index 2), there is no longer an element at index 2; only indices 0 and 1. An exception is raised when we try to remove the non-existent item at index 2, and the loop is stopped. The result is a mangled array that looks like this: ['a', 'd'].

Python doesn't support modifying a list while iterating over it and the right way is to iterate over copy of list instead.


#### 7. What is the "golden rule" of variable scoping in Python (context: LEGB)? What is the lifetime of variables?

The LEGB rule
Namespaces can exist independently from eachother, and have certain levels of hierarchy, which we refer to as their scope. Depending on where you are in a program, a different namespace will be used. To determine in which order Python should access namespaces, you can use the LEGB rule.

LEGB stands for:

Local
Enclosed
Global
Built-in

Namespaces: 
A namespace is a container where names are mapped to objects, they are used to avoid confusions in cases where same names exist in different namespaces. They are created by modules, functions, classes etc.

Scope: 
A scope defines the hierarchical order in which the namespaces have to be searched in order to obtain the mappings of name-to-object(variables). It is a context in which variables exist and from which they are referenced. It defines the accessibility and the lifetime of a variable.

Local Scope: 
Local scope refers to variables defined in the current function. Always, a function will first look up for a variable name in its local scope. Only if it does not find it there, the outer scopes are checked.

Enclosed Scope: 
For the enclosed scope, we need to define an outer function enclosing the inner function otherwise it will be a global variable.

Lifetime:
The Lifetime of a variable is the period throughout which the variable exits in the memory of your Python program. The lifetime of variables inside a function is as long as the function executes. These local variables are destroyed as soon as the function returns or terminates.


#### 8. If you need to access the iterator variable after a for loop, how would you do it in Python?

The for-loop makes assignments to the variables in the target list. This overwrites all previous assignments to those variables including those made in the suite of the for-loop:

        for i in range(10):
            print(i)
            i = 5           # this will not affect the for-loop
                            # because i will be overwritten with the next
                            # index in the range
At the end of the iteration, depending on the outcome (it completes, it breaks), the 'i' variable will keep the last value it received inside the loop.

        example_list = [1, 3, 4]

        for i in example_list:
            print('test')
        print(i)  # prints 4
The iterator variable can be used, but the value has to be carefully considered: Do you want to use the last value it had in the loop? Leave it as it is after the for loop. Do you want to use it in another statement/process/while? Keep in mind that you have to decide if you keep the value or assign a new value. Do you want to use it in a different for loop? This will reset the value inside the new for loop iteration.

#### 9. What type of elements can a list contain in Python?

A list can contain any assortment of objects. The elements of a list can all be the same type, of varying types or can even contain complex objects, like functions, classes, and modules.

#### 10. What is slice operator in Python and how to use?

For any iterable (for eg. a string, list, etc), Python allows you to slice and return a substring or sublist of its data. Format for slicing:

    iterable_name[start:stop:step]
where,

start is the first index of the slice. Defaults to 0 (the index of the first element)

stop one past the last index of the slice. Defaults to len(iterable)

step is the step size (better explained by the examples below) Examples:

        a = "abcdef"
        a               # "abcdef"
                        # Same as a[:] or a[::] since it uses the defaults for all three indices 
        a[-1]           # "f"
        a[:]            # "adcdef"
        a[::]           # "abcdef"
        a[3:]           # "def" (from index 3, to end(defaults to size of iterable))
        a[:4]           # "abcd" (from beginning(default 0) to position 4 (excluded))
        a[2:4]          # "cd" (from position 2, to position 4 (excluded))
In addition, any of the above can be used with the step size defined:

        a[::2]          # "ace" (every 2nd element)
        a[1:4:2]        # "bd" (from index 1, to index 4 (excluded), every 2nd element)
Indices can be negative, in which case they're computed from the end of the sequence

        a[:-1]          # "abcde" (from index 0 (default), to the second last element (last element - 1))
        a[:-2]          # "abcd" (from index 0 (default), to the third last element (last element -2))
        a[-1:]          # "f" (from the last element to the end (default len())
Step sizes can also be negative, in which case slice will iterate through the list in reverse order:

        a[3:1:-1]       # "dc" (from index 2 to None (default), in reverse order)
This construct is useful for reversing an iterable

        a[::-1]         # "fedcba" (from last element (default len()-1), to first, in reverse order(-1))
Notice that for negative steps the default end_index is None.

        a[5:None:-1]    # "fedcba" (this is equivalent to a[::-1])
        a[5:0:-1]       # "fedcb" (from the last element (index 5) to second element (index 1)

#### 11. What arithmetic operators (+,*,-,/) can be used on lists in Python? What do they do?

Lists can be concatenated with the + operator.

        a = [1, 2, 3, 4, 5, 6, 7, 7]
        b = [8, 9, 10]

        a = a + [7, 8] + b
        print(a)        # [1, 2, 3, 4, 5, 6, 7, 7, 7, 8, 8, 9, 10]
Lists can be multiplied with the * operator.

        a = [1, 2, 3, 4, 5, 6, 7, 7]
        b = [8, 9, 10]

        a = a * 2
        print(a)        # [1, 2, 3, 4, 5, 6, 7, 7, 1, 2, 3, 4, 5, 6, 7, 7]
The other operators can't be used on lists, including raising to power.

#### 12. What is the purpose of the in and not in membership operators in Python?

Membership operators are operators used to validate the membership of a value. It tests for membership in a sequence, such as strings, lists, or tuples.

        x = 24
        y = 20
        numbers = [10, 20, 30, 40, 50]
        if x not in numbers:
            print("x is NOT in numbers")
        else:
            print("x is in numbers")
        if y in numbers:
            print("y is present in the given numbers")
        else:
            print("y is NOT present in the given numbers")
        # x is NOT in numbers
        # y is present in the given numbers

#### 13. What does the + operator mean when used with strings in Python?

The + operator performs the concatenation operation between strings, placing the second string at the end of the first to form one final longer string.

        a = 'abra'
        b = 'cadabra'
        print(a+b)
        # abracadabra

#### 14. Explain f strings in Python?

Python f-string is the newest Python syntax to do string formatting. It is available since Python 3.6. Python f-strings provide a faster, more readable, more concise, and less error prone way of formatting strings in Python. The f-strings have the f prefix and use {} brackets to evaluate values.

        name = 'Peter'
        age = 23

        print('%s is %d years old' % (name, age))
        print('{} is {} years old'.format(name, age))
        print(f'{name} is {age} years old')

        # all print
        # Peter is 23 years old

#### 15. Name 4 iterable types in Python!

- string
- list
- tuple
- set
- dictionary

#### 16. What is the difference between list/set/dictionary comprehension and a generator expression in Python?

A list comprehension for example is an elegant way of defining and creating a list. List comprehensions allow us to create lists using a for loop with less code. What normally takes 3-4 lines of code, can be compressed into just a single line.

A generator expression is somewhat similar to a list comprehension, but the former doesn’t construct a list object. Instead of creating a list and keeping the whole sequence in memory, the generator generates the next element in demand. When a normal function with a return statement is called, it terminates whenever it gets a return statement. But a function with a yield statement saves the state of the function and can be picked up from the same state, next time the function is called. The generator expression allows us to create a generator without the yield keyword.

The generator yields one item at a time and generates items only when in demand. Whereas, in a list comprehension, Python reserves memory for the whole list. Thus we can say that the generator expressions are more memory efficient than list comprehensions.

#### 17. Does the order of the function definitions matter in Python? Why?

The order of the function definitions doesn't matter. What matters is when the calling of the function is done, it has to be done after the function has been defined or it will cause a Name Error.

        def print_sum(a, b):
            print(sum_numbers(a, b))

        print_sum(2, 4)

        def sum_numbers(a, b):
            return a + b
This section would cause an error because print_sum is calling sum_numbers inside of it and sum_numbers is defined after. The print_sum call is fine, the second call, the sum_numbers call, will cause the error.

#### 18. What does unpacking mean in Python?

We use two operators * (for tuples) and ** (for dictionaries). Consider a situation where we have a function that receives four arguments. We want to make call to this function and we have a list of size 4 with us that has all arguments for the function. If we simply pass list to the function, the call doesn’t work.

        def fun(a, b, c, d): 
            print(a, b, c, d) 
        
        my_list = [1, 2, 3, 4] 
        
        # This doesn't work 
        fun(my_list)
        # TypeError: fun() takes exactly 4 arguments (1 given)
Unpacking is the action where we use * to manipulate the list so that all elements of it can be passed as different parameters.

        def fun(a, b, c, d): 
            print(a, b, c, d) 

        my_list = [1, 2, 3, 4] 
        
        # Unpacking list into four arguments 
        fun(*my_list)
        # (1, 2, 3, 4)

        >>> range(3, 6)  # normal call with separate arguments 
        [3, 4, 5] 
        >>> args = [3, 6] 
        >>> range(*args)  # call with arguments unpacked from a list 
        [3, 4, 5] 
Packing is the action we take when we don’t know how many arguments need to be passed to a python function. We can use Packing to place all the arguments in a tuple.

        def mySum(*args): 
            sum = 0
            for i in range(0, len(args)): 
                sum = sum + args[i] 
            return sum 
        
        # Driver code 
        print(mySum(1, 2, 3, 4, 5)) 
        print(mySum(10, 20)) 

        # 15
        # 30
The above function mySum() does ‘packing’ to pack all the arguments that this method call receives into one single variable. Once we have this ‘packed’ variable, we can do things with it that we would with a normal tuple. args[0] and args[1] would give you the first and second argument, respectively. Since our tuples are immutable, you can convert the args tuple to a list so you can also modify, delete and re-arrange items in it.

#### 19. What happens when you try to assign the result of a function which has no return statement to a variable in Python?

If the return statement is without an expression, the special value None is returned. If there is no return statement in the function code, the function ends, when the control flow reaches the end of the function body and the value "None" will be returned.


## Software engineering

### Debugging

#### 1. What techniques can you use while debugging a program in Python?

- Rubber Duck: which is the act of a developer explaining their code to a rubber duck in hope of finding a bug
- Print/trace: using print statements inside the code to see how it executes
- Using a Debugger: for example VS Code has a Debugger with advanced features like tracking and breakpoints

#### 2. What does step over, step into and step out mean while using the debugger?

- Step Over: A function is about to be invoked, but you're not interested in debugging this particular invocation, so you want the debugger to execute that function completely as one entire step.
- Step Into: A function is about to be invoked, and you want to debug into the code of that function, so the next step is to go into that function and continue debugging step-by-step.
- Step Out: You're done debugging this function step-by-step, and you just want the debugger to run the entire function until it returns as one entire step.

#### 3. How can you start to debug a program from a certain line using the debugger?

By using a line breakpoint.

Line Breakpoint: You don't care how it got there, but if execution reaches a particular line of code, you want the debugger to temporarily pause execution there so you can decide what to do.

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
