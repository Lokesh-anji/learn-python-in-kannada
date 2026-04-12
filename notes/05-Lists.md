## **Lists in Python**

### **1. What is a List?**

A list is a collection of items that are **ordered**, **mutable** (changeable), and **allow duplicate elements**. Lists can hold items of different data types, such as integers, strings, or even other lists.

**Ordered** means items in a list maintain a specific sequence, and Python preserves that sequence unless explicitly modified.

#### **Syntax**:
```python
my_list = [element1, element2, element3, ...]
```

#### **Example**:
```python
fruits = ["apple", "banana", "cherry"]
numbers = [1, 2, 3, 4, 5]
mixed = ["apple", 3, True]
```

---

### **2. Accessing List Elements**

You can access individual elements in a list using **indexing**. Remember that Python uses **zero-based indexing**, so the first item is at index 0.

#### **Syntax**:
```python
list_name[index]
```

#### **Example**:
```python
fruits = ["apple", "banana", "cherry"]
print(fruits[0])  # Output: apple
print(fruits[2])  # Output: cherry
```

You can also use **negative indexing** to access elements from the end of the list:
```python
print(fruits[-1])  # Output: cherry
print(fruits[-2])  # Output: banana
```

---

### **3. Modifying Lists**
Lists are mutable, which means you can change the value of items in a list.

#### **Changing a specific element**:
```python
fruits = ["apple", "banana", "cherry"]
fruits[1] = "orange"
print(fruits)  # Output: ['apple', 'orange', 'cherry']
```

### **4. Lists Operations/Methods**
- `append()`: Adds an element to the **end** of the list.
  ```python
  fruits = ["apple", "orange", "cherry"]
  fruits.append("grape")
  print(fruits)  # Output: ['apple', 'orange', 'cherry', 'grape']
  ```

- `insert()`: Inserts an element at a **specific index**.
  ```python
  fruits = ["apple", "orange", "cherry"]
  fruits.insert(1, "kiwi")
  print(fruits)  # Output: ['apple', 'kiwi', 'orange', 'cherry']
  ```

#### **Removing elements**:
- `remove()`: Removes the first occurrence of an element.
  ```python
  fruits = ['apple', 'kiwi', 'orange', 'cherry']
  fruits.remove("orange")
  print(fruits)  # Output: ['apple', 'kiwi', 'cherry']
  ```

- `pop()`: Removes the element at a specific index (or the last item if no index is provided).
  ```python
  fruits = ['apple', 'kiwi', 'orange', 'cherry']
  fruits.pop()  # Removes the last item
  print(fruits)  # Output: ['apple', 'kiwi', 'orange']
  
  fruits.pop(0)  # Removes the first item
  print(fruits)  # Output: ['kiwi', 'orange', 'cherry']
  ```

- `clear()`: Removes all elements from the list.
  ```python
  fruits = ['apple', 'kiwi', 'orange', 'cherry']
  fruits.clear()
  print(fruits)  # Output: []
  ```

- `copy()`: Returns a shallow copy of the list.

A **shallow copy** means: you create a new list object, but the elements inside it are not fully copied—they are just references to the same objects in memory.

  ```python
  # Example with mutable objects.

  fruits = ['apple', 'kiwi', 'orange', 'cherry']
  print(fruits)     # ['apple', 'kiwi', 'orange', 'cherry']
  a=fruits.copy()
  print(a)          # ['apple', 'kiwi', 'orange', 'cherry']
  a[0]="banana"
  print(fruits)     # ['apple', 'kiwi', 'orange', 'cherry']  --> origional list not changed, bcz Here in the  example the list "fruit" contains strings of elements ,which are immutable

  print(a)          # ['banana', 'kiwi', 'orange', 'cherry']
#---------------------------------------------------------------#
# Example with mutable objects.

  fruits = [['apple', 'red'], ['kiwi', 'green']]
  print(fruits)      # [['apple', 'red'], ['kiwi', 'green']]
  a=fruits.copy()
  print(a)           # [['apple', 'red'], ['kiwi', 'green']]
  a[0][0]="banana"
  print(fruits)      # [['banana', 'red'], ['kiwi', 'green']]  --> Now origional lists items got changed, Because inner lists are shared (same references)
  print(a)           # [['banana', 'red'], ['kiwi', 'green']]

```
- `count()`: Counts how many times a value appears.
```python
  fruits = ['apple', 'kiwi', 'orange', 'cherry']
  print(fruits.count("apple"))    # 1
```

- `extend()`: Adds elements from another list (or iterable).
```python
  fruits = ['apple', 'kiwi']
  fruits.extend(['orange','cherry'])
  print(fruits)            # ['apple', 'kiwi', 'orange', 'cherry']

  #Iterable example
  fruits = ['apple', 'kiwi']
  a=['orange','cherry']
  fruits.extend(a)
  print(fruits)           # ['apple', 'kiwi', 'orange', 'cherry']
  ```

- `index()`: Returns the position (index) of an element.
```python
  fruits = ['apple', 'kiwi', 'orange', 'cherry']
  print(fruits.index('kiwi'))   # 1
```

- `reverse()`: Reverse the list.
```python
  fruits = ['apple', 'kiwi', 'orange', 'cherry']
  fruits.reverse()
  print(fruits)      # ['cherry', 'orange', 'kiwi', 'apple']
```

- `sort()`: Sorts the list (ascending by default).
```python
  fruits = ['apple', 'kiwi', 'orange', 'cherry']
  fruits.sort()
  print(fruits)    # ['apple', 'cherry', 'kiwi', 'orange']

  num=[1,5,3,6,7]
  num.sort()
  print(num)       # [1, 3, 5, 6, 7]

  fruits = ['apple', 'kiwi', 'orange', 'cherry']
  fruits.sort(reverse=True)
  print(fruits)     # ['orange', 'kiwi', 'cherry', 'apple']

  num=[1,5,3,6,7]
  num.sort(reverse=True)
  print(num)        # [7, 6, 5, 3, 1]
```

---

### **4. Slicing Lists**

You can extract a portion of a list using **slicing**.

#### **Syntax**:
```python
list_name[start:stop:step]
```

- `start`: The index to start the slice (inclusive).
- `stop`: The index to stop the slice (exclusive).
- `step`: The number of steps to skip elements (default is 1).

#### **Examples**:
```python
numbers = [0, 1, 2, 3, 4, 5, 6]
print(numbers[1:4])  # Output: [1, 2, 3] (from index 1 to 3)
print(numbers[:4])  # Output: [0, 1, 2, 3] (from start to index 3)
print(numbers[2:])  # Output: [2, 3, 4, 5, 6] (from index 2 to end)
print(numbers[::2])  # Output: [0, 2, 4, 6] (every 2nd element)
```

---

### **5. List Functions and Methods**

Python provides several built-in functions and methods for working with lists.

#### **5.1 Common Functions**:
- `len(list)`: Returns the number of elements in the list.
  ```python
  print(len(fruits))  # Output: 3
  ```

- `sorted(list)`: Returns a new sorted list without changing the original list.
  ```python
  numbers = [5, 2, 9, 1]
  print(sorted(numbers))  # Output: [1, 2, 5, 9]
  print(numbers)  # Original list remains unchanged: [5, 2, 9, 1]
  ```

- `sum(list)`: Returns the sum of elements in a list (for numerical lists).
  ```python
  numbers = [1, 2, 3, 4]
  print(sum(numbers))  # Output: 10
  ```

---

### **6. Nested Lists**

Lists can contain other lists, allowing you to create **nested lists**. This can be useful for storing matrix-like data structures.

#### **Example**:
```python
matrix = [
    [1, 2, 3],
    [4, 5, 6],
    [7, 8, 9]
]

# Accessing elements in a nested list
print(matrix[0])  # Output: [1, 2, 3] (first row)
print(matrix[1][1])  # Output: 5 (element in the second row, second column)
```

---

### **Homework**

1. **List Manipulation Exercise**:
   - Create a list of 5 items (strings or numbers).
   - Add a new item to the end of the list and another at the second position.
   - Remove the third item from the list.
   - Print the list after each operation.

2. **Reverse and Sort a List**:
   Create a list of numbers and:
   - Sort it in descending order.
   - Reverse the sorted list and print it.

---

Watch the following YouTube video from my channel:
- [Watch the tutorial on YouTube](https://youtu.be/bvohjRepLz0?si=8teUh_H3hqwdNpaZ)


 Make sure to subscribe to the channel for more Python tutorial and updates! 