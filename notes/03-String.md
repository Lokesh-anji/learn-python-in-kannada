## **Input/Output, String Manipulation, and Comments**

### **1. Input and Output in Python**

#### **1.1 Input from the User:**
In Python, we use the `input()` function to take input from the user. The data entered by the user is always received as a string, so if you want to use it as a different data type (e.g., integer or float), you'll need to convert it using type conversion functions like `int()` or `float()`.

```python
name = input("Enter your name: ")
age = int(input("Enter your age: "))  # Convert input to integer
```

#### **1.2 Output to the Console:**
The `print()` function is used to display output to the console. You can use it to display text, variables, or results of expressions.

```python
print("Hello, " + name + "! You are " + str(age) + " years old.")
```

You can also use **f-strings** (formatted string literals) for more readable code:
```python
print(f"Hello, {name}! You are {age} years old.")
```

---

### **2. String Manipulation**

A string is an immutable sequence of characters enclosed in quotes, used to represent text in Python.. Python provides many useful methods to manipulate strings.
 
#### **2.1 Common String Operations:**

- **Concatenation**: Joining two or more strings together using the `+` operator.
  ```python
  first_name = "John"
  last_name = "Doe"
  full_name = first_name + " " + last_name
  print(full_name)  # Output: "John Doe"
  ```

- **Repetition**: Repeating a string multiple times using the `*` operator.
  ```python
  greeting = "Hello! " * 3
  print(greeting)  # Output: "Hello! Hello! Hello! "
  ```

#### **2.2 String Methods:**
- `upper()`: Converts a string to uppercase.
- `lower()`: Converts a string to lowercase.
- `strip()`: Removes leading and trailing spaces from a string.
- `replace(old, new)`: Replaces a substring with another string.

```python
message = "  Hello, World!  "
print(message.upper())  # Output: "HELLO, WORLD!"
print(message.lower())  # Output: "hello, world!"
print(message.strip())  # Output: "Hello, World!"
print(message.replace("World", "Python"))  # Output: "Hello, Python!"
message = "hello, World!, Python"
print(message.capitalize()) # Output: "Hello, world!, python"
message = "Hello, World!, Python"
print(message.casefold()) # Makes lower-case Output: hello, world!, python

#title() ➡️ First letter of each word uppercase
print("hello world".title())   # Output: Hello World

#swapcase() ➡️ Converts uppercase ↔ lowercase
print("HeLLo".swapcase())   # Output: hEllO

#find() ➡️ Returns index of first occurrence (-1 if not found)
print("python".find("t"))   # 2
print("python".find("k"))   # -1

#rfind ➡️ Searches from right side
print("banana".rfind("a"))   # 5

#index() ➡️ Same as find() but gives error if not found
print("python".index("y"))   # 1
print("python".index("k"))   # ValueError: substring not found

#count() ➡️ Counts occurrences
print("banana".count("a"))   # 3
print("banana".count("k"))   # 0

#startswith() ➡️ Returns true if the string starts with the specified value.
print("python".startswith("p"))   # True
print("python".startswith("k"))   # False

#endswith() ➡️ Returns true if the string ends with the specified value.
print("python".endswith("n"))   # True

#isalpha() ➡️ Returns True if all characters in the string are in the alphabet.
print("python".isalpha())   # True
print("python ".isalpha())   # False

#isdigit() ➡️ Returns True if all characters in the string are digits
print("123".isdigit())   # True
print("123 as".isdigit())   # False

#isalnum() ➡️ Returns True if all characters in the string includes Letters + numbers.
print("python".isalnum())   # True
print("python12".isalnum())   # True
print("python@".isalnum())   # False

#isspace() ➡️ Returns True if all characters in the string are whitespaces.
print(" ".isspace())   # True
print("".isspace())   # False

#islower() ➡️ Returns True if all characters in the string are lower case.
print("python".islower())   # True
print("Python".islower())   # False

#isupper() ➡️ Returns True if all characters in the string are upper case
print("Python".isupper())  # False
print("PYTHON".isupper())  # True

#center() ➡️ Print the word "hi", taking up the space of 10 characters, with "banana" in the middle:
print("hi".center(10, "-"))   # ----hi----

#encode() ➡️ converts a string into bytes using a specific encoding format (default is UTF-8).
print("python".encode())   # b'python'

#join() ➡️ The join() method takes all items in an iterable and joins them into one string.
my_list=["lokesh","Anji"]
b="-".join(my_list)
print(b)           # lokesh-Anji
print(type(b))     # <class 'str'> 

#split() ➡️ is used to convert a string into a list by breaking it at a separator.
a="My name - is Lokesh"
print(a.split())       # ['My', 'name', '-', 'is', 'Lokesh']    
print(a.split("-"))    # ['My name ', ' is Lokesh']

#len() ➡️ provides the len of the string.
a="Lokesh"
print(len(a))       # 6 

```

#### **2.3 Accessing String Characters:**
You can access individual characters in a string using **indexing**. Python uses zero-based indexing, so the first character has an index of 0.

```python
text = "Python"
print(text[0])  # Output: P
print(text[2])  # Output: t
```

You can also use **negative indexing** to start counting from the end of the string.
```python
-5 -4 -3 -2 -1  0  1  2  3  4
print(text[-1])  # Output: n
print(text[-3])  # Output: h
```

#### **2.4 Slicing Strings:**
You can extract a portion (substring) of a string using slicing.

```python
text = "Python Programming"
print(text[0:6])  # Output: Python (extracts from index 0 to 5)
print(text[:6])  # Output: Python (same as above)
print(text[7:])  # Output: Programming (from index 7 to the end)

[Start:End:Step]
#By default 'Step' is 1
```

---

### **3. Comments in Python**

Comments are ignored by the Python interpreter and are used to explain the code or leave notes for yourself or others. They do not affect the execution of the program.

- **Single-line comments** start with `#`:
  ```python
  # This is a single-line comment
  print("Hello, World!")
  ```

- **Multi-line comments** can be written using triple quotes (`"""` or `'''`). These are often used to write detailed explanations or temporarily block sections of code:
  ```python
  """
  This is a multi-line comment.
  It can span multiple lines.
  """
  print("Hello, Python!")
  ```

---

### **4. Escape Sequences**
Escape sequences are special characters in strings that start with a backslash (`\`). They are used to represent certain special characters.

Some commonly used escape sequences:
- `\n`: New line
- `\t`: Tab space
- `\\`: Backslash

#### **Example:**
```python
print("Hello\nWorld")  # Output: 
# Hello
# World

print("Hello\tPython")  # Output: Hello    Python
```

---

### **Homework**

1. **Simple Greeting Program**:
   Write a Python program that asks the user for their name and age, then prints a personalized greeting message. Use both the `+` operator and f-strings for output.

   **Example**:
   ```python
   Enter your name: Alice
   Enter your age: 25
   Output: Hello, Alice! You are 25 years old.
   ```

2. **String Manipulation Exercise**:
   Write a Python program that:
   - Takes a sentence as input from the user.
   - Prints the sentence in all uppercase and lowercase.
   - Replaces all spaces with underscores.
   - Removes leading and trailing whitespace.

   **Example**:
   ```python
   Input: "   Python is awesome!   "
   Output:
   Uppercase: "PYTHON IS AWESOME!"
   Lowercase: "python is awesome!"
   Replaced: "___Python_is_awesome!___"
   Stripped: "Python is awesome!"
   ```

3. **Character Counter**:
   Write a Python program that:
   - Asks the user for a string.
   - Prints how many characters are in the string, excluding spaces.

   **Example**:
   ```python
   Input: "Hello World"
   Output: "Number of characters (excluding spaces): 10"
   ```

4. **Escape Sequence Practice**:
   Write a Python program that uses escape sequences to print the following output:

   **Example**:
   ```
   Hello
       World
   This is a backslash: \
   ```

---

### **YouTube Reference**
Watch the following YouTube video from my channel:
- [Watch the tutorial on YouTube](https://youtu.be/0qo3QEidzjA?si=B_yq5Mg02EjlJNQ9)


 Make sure to subscribe to the channel for more Python tutorial and updates! 