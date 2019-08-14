# Introduction to Python Programming

Python development mostly requires no overhead from beginner developers.

Consider the code below written in Java:

```java
public class HelloWorld {
    public static void main(String[] args) {
        // Prints "Hello, World" to the terminal window.
        System.out.println("Hello, World");
    }
}
```

The only code we're really interested in here is ``System.out`` ... and even that in itself is slightly cryptic. What does System, out, and println stand for? why are they required? All of this code is important for seasoned developers but for newbies who have no knowledge of object oriented programming or the `System` namespace would likely have a hard time understanding what each and every code is used for.

## Your first Python Code

Let's now compare that to a python code. First, let's create a fresh file in our notebook. In your Jupyter notebook, click on `File`, `New Notebook` then click `Python 3`:

![](/img/fig-04-new-notebook.png)

Then in one cell, write the code:

```
print("Hello, World")
```

Click "Run" and it should print out the string your specified.

__Congratulations!__ You just became a programmer!

## Variables

Variables are keywords you define, they are used to represent a certain value that can be changed on run time.

Writing a variable should look something like:

```python
name = "Ervinne Sodusta"
```

Where `name` is the name of the variable and the words to the right of the `=` sign is called a value, specifically, a "String" value.

You can use any letter, the special characters "_" and every number provided
you do not start with it. 

We may then use a variable in a `print` function:

```python
name = "Ervinne Sodusta"
print(name)
```

This is not very interesting though as the variable here is "constant". Thus, does not provide any real value to us. To make variables actually "variable", let's make use of the `input` function to ask the user of our notebook for an input:

```python
name = input("What's your name boy?")
print(name)
```

This will then printout the string you specified with a text box beside it where you may input any string. The value you specified will then be "assigned" to the `name` variable which we can then use in other statements.

### Concatenating Strings

You may use the `+` operator to "add" or more specifically, concatenate strings:

```python
firstName = input("First Name: ")
lastName = input("Last Name: ")

print(firstName + " " + lastName)
```

### Data Types

A data type is the way a variable is stored and utilized within the computer. So far, we've explored strings in Python, below are other data types:

- `Integer` types are whole numbers: `age = 23` 
- `Float` types are decimals: `weight = 60.4`
- `String` is what we already been dealing with: `name = "Ervinne"`
- `Boolean` types represent `true` or `false`: `isDoneProcessing = true`

## Simple Arithmetic

You may do simple arithmetic with values and variables in coding. For example:

```python
x = input("x: ")
print(x + 5)
```

But this will generate an error pointing to `print(x + 5)` saying that the integer `5` must be a string. The problem isn't really on this line because we really intend to add two integers, the real problem, is that the value of the variable `x` is a string, not an integer. So we modify our code to:

```python
x = int(input("x: "))
print(x + 5)
```

We just told python to get a value, convert it from string to integer before assigning it to the variable `x` so we may do proper arithmetic to it.

The `int` function is used to convert the value provided by `input` from string to an integer. This is called "casting". Casting is when you convert a variable value from one type to another. This is, in Python, done with functions such as `int()` or `float()` or `str()`.

Common arithmetic operations are:

- Addition: `+`
- Subtraction: `-`
- Multiplication: `*`
- Division: `/`
- Exponents: `**` ex: 𝑥<sup>2</sup> is `x ** 2`

You may have noticed that we're using familiar terminologies like functions and variables in mathematics. That's because that's exactly what functions and variables in math means.

For example, the function of x:

𝑓(𝑥)=2𝑥<sup>2</sup>+4𝑥+6 

Can be written in Python as:

```python
x = int(input("Evaluate f(x) with x equals: "))
fx = 2 * x ** 2 + 4 * x + 6
print(fx)
```

## Functions

You might be wondering what `input` and `print` and `int` are. These keywords are called `functions` a function is a keyword in python that when "called" or "invoked" does a certain operation.

For example, the `input` function takes in an string `argument` which it displays when asking for an input, then takes our input and `returns` an output.

```python
int(x)
```

An `argument` is anything that we pass in to a function as an input enclosed with open and closed parenthesis. In this case, the `x` variable.

## Creating Your Own Functions

Functions are just operations that are also created by other developers in advanced so we can use later on, like `print` and `input`. With that in mind, we can also create our own functions ourselves.

To define a function, we will use the `def` keyword and the following syntax:

```python
def convert_celsius_to_farenheit(temp):
    return 9/5 * temp + 32
```

You may then invoke this function by:

```python
farenheit = convert_celsius_to_farenheit(20)
print(farenheit)
```

You may also want more than one parameters to a function, like say when you want to get the area of a triangle

```python
def get_triangle_area(base, height):
    return 1/2 * base * height
```

## Lambda Functions

Lambda functions are function without a name, they are also called anonymous functions.

While normal functions are defined using the def keyword, in Python anonymous functions are defined using the lambda keyword.

These kinds of function are usually passed in as arguments but may also be assigned as a value of a variable. That variable, may then behave as a function. For example, lets convert convert_celsius_to_farenheit to a lambda function:

```python
convert_celsius_to_farenheit = lambda temp: 9/5 * temp + 32
```

Multiple parameter lambda functions will need to have its parameters separated by commas

```python
get_triangle_area = lambda base, height: 1/2 * base * height
```

It may not make sense right now why lambda functions exists, but later on, we will make proper use of them to really reap their benefits. For now, keep their syntax in mind.

## Control Statements Pt1: Conditional Statements

Control statements are statements in your code that alter the flow of execution. If you've noticed, code runs in a straight forward manner - going from top to bottom.

We'll first explore the conditional statements:

### `if` Statement
`if` statement tests if a given expression is `true` (boolean), if it is, it executes the *indented* code below it. For example:

```python
userIsAdmin = True
if userIsAdmin:
    print("The user is an administrator") # should print
```

or

```python
userIsGuest = False
if userIsGuest:
    print("The user is a guest") # nothing should happen
```

### `elif` Statement

`elif` stands for "else, if ...". This means that if the previous if statement is false, try this statement instead. For example:

```python
userIsAdmin = True
userIsGuest = False

if userIsAdmin:
    print("The user is an administrator")
elif userIsGuest:
    print("The user is a guest")
```

### `else` Statement

Lastly, the `else` statement is for when all the conditional statement fails, the operations below the `else` keyword gets invoked:

```python
userIsAdmin = False
userIsGuest = False

if userIsAdmin:
    print("The user is an administrator")
elif userIsGuest:
    print("The user is a guest")
else:
    print("The user is neither administrator nor a guest")
```

To make conditionals actually useful, we need to be able to test for values of a variable.

### Comparing Values

Programmers are able to compare between two or more values using what we call "Relational Operators" and "Logical Operators"

#### Relational Operators

Relational operators compare two values using the following operators:

|Operator|Description|Example Expression|
|-|-|-|
| == | Tests for equality | x == y |
| != | Tests if the two value are not equal | x == y |
| > | Test if the lhs value is greater than the rhs | x > y |
| < | ^ Vise versa | x < y |
| >= | Test if lhs is greater than or equal to the rhs | x >= y |
| <= | ^ Vise versa | x <= y |

Examples:

```python
secretKey = input("Tell me the secret key and I'll tell you the secret phrase: ")

if secretKey == "jollibee":
    print("I love you sabado")
else:
    print("You don't know the secret")
```

Simple guessing Game Version 1

```python
secretNumber = 13
userGuess = int(input("Guess my secret number"))

if userGuess == secretNumber:
    print("You're good")
elif userGuess < secretNumber:
    print("No, it's a little higher than that")
else:
    print("No, it's a little lower than that")
```

What if we don't want the code to stop until we get the number right? We'll learn that later on when we do loops.

#### Logical Operators

Logical operators are useful for when you have multiple relational operations to test:

|Operator|Description|Example Expression|
|-|-|-|
| and | Test if both lhs and rhs is true | x and y |
| or | Test if either side is true | x or y |

Examples:

Testing for Float Ranges: A student grade converter

```python
studentGrade = float(input("Input your grade: "))
convertedGrade = "invalid"

if studentGrade <= 100 and studentGrade >= 97:
    convertedGrade = 1.0
elif studentGrade <= 96 and studentGrade >= 93:
    convertedGrade = 1.5

# ... and so on up to 5.0

print(convertedGrade)
```

## Control Statements Pt1: Looping Statements

Looping statements are for when you want a certain operation to run again and again until a certain condition is still true, or you want your code to run through lists, or go through a range.

### For Loop

Such loops are useful for looping through a range of numbers or a list. A list is a value that contains multiple values. For example:

```python
attendees = [ "Khael", "Philip", "Pam", "Enzo", "Nova" ]
```

`for` loops, go through lists like so:

```python
attendees = [ "Khael", "Philip", "Pam", "Enzo", "Nova" ]
for name in attendees:
    print(name)
```

It's also useful if you want to loop through a range of numbers, for example:

```python
for number in range(1, 10):
    print(number) # will print 1 to 9
```

### While Loop

While loops make the code run while a given condition is still true. For example, let's modify our simple guessing game to not stop until we enter the correct number:

To do this, we need to be able to generate a random number first. For this, we'll need to "import" a library. A library is a collection of code that you may reuse:

```python
import random

secretNumber = random.randint(5, 20)

# Milestone! Let's check first if random really works before we integrate the guessing game
print(secretNumber)
```

Now, we can do the actual loop:

Simple guessing Game Version 2

```python
import random

secretNumber = random.randint(5, 20)

userGuess = int(input("Guess my secret number: "))

while secretNumber != userGuess:
    if userGuess < secretNumber:
        print("No, it's a little higher than that")
    else:
        print("No, it's a little lower than that")

    userGuess = int(input("Guess my secret number: "))

print("You got it!")
```

__Danger!__ You should notice that it's possible to unintentionally generate infinite loops. This will make your code run over and over again without stopping!. In fact, if we forgot the duplicate of getting userGuess, it will ask us infinitely.

### Segue: Basic Refactoring: Dry Code

You should notice that we have two exactly same code in different lines. You code may work but this is wrong. This is called a code smell.

Code smells are code defects that may not present problems now, but will likely do in the future. For example, if we change the prompt in the first assignment of `userGuess` but forgot in in the second, we produce the issue of inconsistency.

In this very specific case, using a `while` loop is wrong. Other languages has a concept of a `do` ... `while` loop. Python does not, so we'll have to work around this:

```python
import random

secretNumber = random.randint(5, 20)

while True:
    userGuess = int(input("Guess my secret number: "))
    if userGuess == secretNumber:
        print("You got it!")
        break
    elif userGuess < secretNumber:
        print("No, it's a little higher than that")
    else:
        print("No, it's a little lower than that")
```