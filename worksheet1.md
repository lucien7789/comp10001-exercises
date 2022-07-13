# Data types

### There are 4 main data types you should know about

**String, textual data, no numerical information**  
```python
'Strings can be created with the quotation marks'
"Double quotation marks work as well"
'You can use strings to present information or ask the user for specific input'
''
```
**Integer, numerical data, whole numbers**
```python
123
12
1
```
**Float, decimal value numbers**
```python
0.2
2.35
4.0
```
**Boolean, true or false**
```python
True
False
```

# Numerical operations
You can perform numerical operations on integers and floats
```python
1 + 2 # Plus
1 - 2 # Minus
1 * 2 # Multiplication
1 / 2 # Division
1 // 2 # Integer division, divides the number, but removes any decimals, eg. 3 // 2 = 1 (we remove the .5)
1 % 2 # Modulus (Gets remainder after division, eg. 12 % 10 = 2)
1 ** 2 # 1 to the power of 2 (which is 1)

# You can also use ints and floats together
2 * 0.5 # 1
0.33 * 2 # 0.66

1 / 10 # 0.1
```
**Note that we created a float ```0.1``` by dividing 2 integers ```1```, ```10```.  
You can also order the operations using brackets
```python
1 * (1 + 2)
(1 + 1) * (2 + 2)
```
_NOTE: By default, python uses BODMAS to order operations_

# Declaring variables

### To declare a variable use the '=' operator, you can assign any data type to any variable
```python
myVariableName = 10

stringVariable = 'string'

### You can also assign variables to other variables

variableA = 1
variableB = variableA
```
# Input and Output

In python, you can use the functions input() and print() to read user input and output values


The input function takes a string as an argument, this string will be used to prompt for input
```python
name = input('please enter your name: ')
```
The input function returns a string ("returns" sounds weird, but it simply means the function outputs a value)

So if we want to use numerical operations on an input, we need to convert it to an integer or float
```python
age = input('please enter your age: ')
ageAsInt = int(age)
ageAsFloat = float(age)

#### NOTE: Be careful with using the int() function on strings with decimal values, this will cause an error,
#### Eg. int('3.1') will fail because the string cannot be converted
```

### Print function
The print function takes in an infinite amount of arguments, of any type, each will be outputted to the user console.
```python
print('hello world')
print('my age is', 12)

### We can also pass variables in place of literal values
myName = 'Guitar'
print("hi there, 'im", myName)
```

**NOTE: It's not just the print function, for any function or operation, we can use a variable in place of a value**

# If/Elif/Else Statements

### How do we do something based on a particular condition? 
The answer is to use if/elif/else statements.

The structure goes like this
```python
if condition:
    # Do something
elif condition:
    # Do something
else:
    # Do something
```

The elif and else statements are optional.

**NOTE: The conditions are checked in order, if there are multiple valid conditions, only the first condition will be used.**

### What is a condition? 
A condition is an expression that is either one of two values - **True** or **False**.

```python
3 < 4 # This is True
4 < 3 # This is false
'name' == 'name' # This is true
len([1,2,3,4]) == 4 # This is true
len('abc') == 3 # This is true
```

There are some common comparison operators:
```python
< # Less than
<= # Less than or equal to
> # Greater than
>= # Greater than or equal to
== # Equals
```
### Using conditions for if/else
Here is a simple program that prompts the user for their age, and checks if they are allowed to drive.
```python
age = int(input('please enter your age: '))

if age < 16:
    print('sorry, you are too young! you need another', 16 - age, 'years to drive cars')
else:
    print('you can drive')
```
However, we are missing crucial logic, what if the user inputs a negative number? This is where we use elif.
```python
age = int(input('please enter your age: '))

if age < 0:
    print("you're lying")
elif age < 16:
    print('sorry, you are too young! you need another', 16 - age, 'years to drive cars')
else:
    print('you can drive')
```

Finally, what if the user doesn't have a license?
How do we check for both a license and age?

This is where the compound conditionals come in:

There are two main keywords in creating compounds.
```python
and
or
```

We can use these keywords to connect conditionals, like this:
```python
age = int(input('please enter your age: '))
license = input('do you have a license? Y/N')

if age < 0:
    print("you're lying")
### If the user is too young, OR he doesn't have a license, then he isnt allowed to drive
elif age < 16 or license == 'N':
    print('sorry, you are too young! you need another', 16 - age, 'years to drive cars')
else:
    print('you can drive')
```

# Lists

How do we store multiple values into a single variable? We can use a data structure. The very first data structure we come across is List.

Simply a sequential ordering of elements.

**To declare a list**
```python
myList = [1,2,3,4] # We use the square brackets

### We can also declare an empty list
emptyList = []
```

**To access an element in a particular list**
```python
myList[index]

### Indexes begin at 0 and end at the length of the list - 1

### So to access the first element of myList
myList[0]

### Second element
myList[1]

### We can also use negative indices, which go from the end of the list

### To get the last element
myList[-1]
myList[len(myList) - 1]

### To get the second last element
myList[-2]
myList[(len(myList) - 2)]
```

Note that we used the len() function, this is a useful function that gives us the length of a list, or string, or any data structure.
```python
len([1,2,3,4]) = 4
len(['a','b','c','d']) = 4
len('abcd') = 4
len([]) = 0
len('') = 0
```

## Modifying lists
What if we want to change a list?

How do we do this?

There is a _method_ for adding elements.
```python
myList.append(element)
```

There is also a method for removing elements.
```python
myList.pop(indexOfElement)
```

**Methods will be covered later but they are essentially a special type of function binded to a type**

They are called in the form
```python
value.methodName()

### Different to a function
functionName()
```
# "In" Keyword
The ```in``` keyword is a special keyboard that can act as a check whether or not an element exists.

For example:
```python
5 in [1,2,3,4,5] # True
'a' in 'abc' # True
'd' in 'abc' # False
'hello' in 'hello world' # True
```

We can use them as part of our if/else statements.

```python
registeredNames = ['apple', 'guitar', 'piano', 'kevin']
name = input('please enter your name:')

if name in registeredNames:
    print('your name is registered!')
else:
    print('you need to register!')
```
# While/For Loops
How do we repeat an action or code? We can use the while or for loop code  structure.

**First, the while loop:**
```python
while condition:
    # Do something
```

A simple example of printing every element in a list.
```python
myList = [1,2,3,4,'a','b','c','d']
i = 0
while i < len(myList):
    print('The element at', i, 'is', myList[i])
    i = i + 1
```

Another example of adding up all the numbers up to N.
```python
n = input('please enter a number: ')
mySum = 0
i = 0
while i < n:
    mySum = mySum + i
    i = i + 1
print('your sum is', mySum)
```

**Next, the for loop:**
```python
for element in sequence:
    # Do something
```
**NOTE: A sequence is something like a string, list, range, etc.**

The ```element``` declared after the ```for``` will hold the value of every element in ```sequence```

To print out all the elements in a sequence:
```python
myList = ['python','is','so','easy']

for elem in myList:
    print(elem)

### We can also loop over strings

myString = 'my name'
for character in myString:
    print(character)
```

There is a range function that produces a "range" type. This range type is like a list.
```python
range(10) # equivalent to [0,1,2,3,4,5,6,7,8,9]
range(8, 10) # equivalent to [8,9]

# We can also specify a third argument, which defines the "step"
range(0, 10, 2) # equivalent to [0,2,4,6,8]

# We can also use negative steps, which go in reverse
range(10, 0, -1) # equivalent to [10,9,8,7,6,5,4,3,2,1]
```

Since the range type is a sequence, we can iterate over it.
```python
for i in range(10):
    print(i)
# Output:
# 0
# 1
# 2
# 3
# 4
# 5
# 6
# 7
# 8
# 9
```

We can also do some smart things with a list.
```python
myList = ['ni','hao','wo','she','ice','cream']
### Remember that the range() function excludes the upper bound
### And the last element of a list is len(myList) - 1
### So this will loop perfectly over every index
for i in range(len(myList)):
    print('value at index', i, 'is', myList[i])
```

# Functions
We have been using some predefined functions like:
```python
len()
input()
int()
range()
print()
```
Let's define our own function now.

To define a function:
```python
def functionName(arguments):
    # Do something
```
We can then call this function:
```
functionName(arguments)
```

Let's make a Hello World function.
```python
def helloWorld():
    print('hello world')
```

We then call it:
```
helloWorld()
```

## Returning values
Remember how some functions like ```len()``` or ```input()``` outputting or "returning" values?  
_How do we do this?_

We need to use the keyword:
```python
return
```

This basically tells the function to stop and output the value, any code beyond return will not be executed

For example, a function that gives a constant value
```python
def giveMeAFour():
    return 4
```

Now we can call this function and assign the output to a variable
```python
value = giveMeAFour()
print(value) # 4
```
Or a function that adds 3 elements together
```python
def addThree(a, b, c):
    return a + b + c
```
We can also use any of the above code structures in functions
```python
def isAbleToDrive(age):
    if (age < 16):
        return False
    else:
        return True
```
Let's finish this section off with a more useful function.

```python
def combineLists(listA, listB):
    combinedList = []

    # Add all the elements of listA
    for elem in listA:
        combinedList.append(elem)

    # Add all the elements of listB
    for elem in listB:
        combinedList.append(elem)

    return combinedList
```

We can then call this function:
```python
listA = ['a','b','c']
listB = [1,2,3]
combinedList = combineLists(listA, listB)
print(combinedList) # ['a','b','c',1,2,3]
```

# Finally
Here are some useful predefined functions and methods.

```python
sum() # Takes in a list or multiple numbers and sums them
```

**sum()**
```python
sum([1,2,3]) # 6
sum(1,2,3) # 6
sum([]) # 0
```

```python
string.lower() # Returns a string with all the characters lowercase
string.upper() # Returns a string with all the characters uppercase
```

**list()**
```python
list(sequence) # Converts a sequence to a list
```

```python
list(range(10)) # [0,1,2,3,4,5,6,7,8,9]
list("hello world") # ['h','e','l','l','o',' ', 'w','o','r','l','d']
```
**string.lower() string.upper()**
```python
"ABCDE".lower() # "abcde"
mystring = "123Abc"
mystring.lower() # "123abc"

"abcde".upper() # "ABCDE"
```

**list.index()**
```python
myList.index(elem) # Takes in an element and finds the index of the element
```

```python
[1,2,3].index(1) # 1
[1,2,3].index(4) # Causes an error
[1,2,3,3].index(3) # 2 (returns the first occurance)
```
# Exercises
## **1.** Are you John?
Write a function that prints out 'Hi John' if the argument is a string with 'john' in it.

Otherwise, print 'Sorry, I only talk to John'

Complete the following function:
```python
def johnCheck(value):
    # Your code
```

**Test cases**
```python
johnCheck('john')
'Hi John'

johnCheck('johjohjoh')
'Sorry, I only talk to John'

johnCheck('jojo john')
'Hi John'

johnCheck('kevin')
'Sorry, I only talk to John'
```
## **2.** Hypotenuse calculator
Write a function that calculates the hypotenuse of a right angle triangle given the other two side lengths.

Complete the following function:
```python
def hypotenuse(sideA, sideB):
    # Your code
```

**Test cases**
```python
hypotenuse(3,4)
Output: 5

hypotenuse(9, 12)
Output: 15

hypotenuse(600, 800)
Output: 1000
```
## **3.** Primary School Division
Write a function that takes in a value and a divisor.

The function should divide the value by the divisor with remainders.

Your function should print the result in the form of
```
'Value: x, Remainder: y'
```
For example:
```python
divideWithRemainder(5, 3)
'Value: 1, Remainder: 2'
```

Complete the following function:
```python
def divideWithRemainder(value, divisor):
    # Your code
```

**Test cases**
```python
divideWithRemainder(2, 1)
'Value: 2, Remainder: 0'

divideWithRemainder(10, 3)
'Value: 3, Remainder: 1'

divideWithRemainder(12, 5)
'Value: 2, Remainder: 2'

divideWithRemainder(1.1, 1)
'Value: 1, Remainder: 0.1'
```
## **4.** All Even
Write a function that takes in a value N and returns a list of all the positive even numbers smaller than N

Complete the following functon:
```python
def allEven(N):
    # Your code
```

**Test cases**
```python
allEven(4)
Output: [2]

allEven(5)
Output: [2,4]

allEven(10)
Output: [2,4,6,8]

allEven(1)
Output: []
```
## **5.** Odd or even?
Write a function that checks if a number is odd or even.  

If it is odd: print ```'your number is weird'```

If it is even: print ```'lovely number'```

Complete the following function:
```python
def checkNumber(number):
    # Your code
```

**Test cases**
```python
checkNumber(2)
'lovely number'

checkNumber(0)
'lovely number'

checkNumber(1)
'your number is weird'

checkNumber(-1)
'your number is weird'
```
## **6.** Remove element if exists

Write a function that takes in a list and a value.
If that value exists in the list, remove the first instance of that value from the list.

**NOTE: Your code doesn't need to return the modified list, it just needs to modify the list.**

Complete the following function:
```python
def removeElementIfExists(myList, elem):
    # Your code
```

**Test cases**
```python
listA = [1,2,3]
removeElementIfExists(listA, 4)
Result: listA = [1,2,3]

listB = ['a','b','c']
removeElementIfExists(listB, 'c')
Result: listB = ['a','b']

listC = ['one','two','one','two']
removeElementIfExists('two')
Result: listC = ['one','one','two']
```
## **7.** If not smaller, remove.

Write a function that takes in a list and a number,
then outputs a new list with all the elements smaller than value.

Complete the following function:
```python
def onlySmallerThan(myList, value):
    # Your code
```

**Test cases**
```python
onlySmallerThan([1,2,3,4], 0)
Output: []

onlySmallerThan([-1,-2,-3,-4], 0)
Output: [-1,-2,-3,-4]

onlySmallerThan([100, 1, 80, 8], 100):
Output: [1, 80, 8]
```

## **8.** Reversing a list
Write a function that takes in a list and reverses it.  
Complete the following function:
```python
def reverseList(myList):
    # Your code
```

**Test cases**
```python
reverseList([])
Output: []

reverseList([1,2,3])
Output: [3,2,1]

reverseList(['a',11,'b',12])
Output: [12,'b',11,'a']
```

## **9.** Does it contain vowels?
Write a function that checks if a string contains vowels.

Complete the following function:
```python
def containsVowels(string):
    # Your code
```

**Test cases**
```python
containsVowels('a1b2c3d4e5')
Output: True

containsVowels('PYTHON')
Output: True

containsVowels('horsE')
Output: True

containsVowels('abc')
Output: False

containsVowels(''):
Output: False
```

## **10.** Strict length list
Write a function that takes in a list and a value which is the desired length of the list.

If the length of the list is smaller than the value, add additional 'a' elements to the end of the list to make the list the correct size.

If the length of the list is bigger than the value, remove elements from the end of the list until it is the correct size.

Complete the following function:
```python
def enforceLength(myList):
    # Your code
```

**Test cases**
```python
enforceLength([], 0)
Output: []

enforceLength([1,2,3], 3)
Output: [1,2,3]

enforceLength(['this','list','is','a','bit','long'], 4)
Output: ['this','list','is','a']

enforceLength(['too','short'], 3)
Output: ['too','short','a']
```

## **Challenge.** Fibonacci
A Fibonacci sequence is the sum of numbers:
```python
## The first two numbers are 1 and 1, the numbers afterwards are the sum of it's previous two
## Eg. 8 = 3 + 5, 13 = 5 + 8
1, 1, 2, 3, 5, 8, 13, 21, 34
```
Write a function that outputs the nth Fibonacci number starting from 0.  
Complete the following function:
```python
def fib(n):
    # Your code
```

**Test cases**
```python
fib(0)
Output: 1

fib(1)
Output: 1

fib(4)
Output: 5

fib(9)
Output: 55

fib(42)
Output: 165580141
