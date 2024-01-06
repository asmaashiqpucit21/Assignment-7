```python
                                             #Assignment-07 (Exceptions)
#"Write a Python program that demonstrates a simple try-except block to handle a ZeroDivisionError."
def divide_numbers(a, b):
    try:
        result = a / b
        print(f"The result of {a} divided by {b} is: {result}")
    except ZeroDivisionError:
        print("Error: Division by zero is not allowed.")
    except Exception as e:
        print(f"An unexpected error occurred: {e}")

# Example:-
try:
    numerator = int(input("Enter the numerator: "))
    denominator = int(input("Enter the denominator: "))
    divide_numbers(numerator, denominator)
except ValueError:
    print("Error: Please enter valid numerical values.")
except Exception as e:
    print(f"An unexpected error occurred: {e}")

```

    Enter the numerator: a
    Error: Please enter valid numerical values.
    


```python
 "What is the purpose of the else clause in a try-except block? Provide an example."
def divide_numbers(a, b):
    try:
        result = a / b
    except ZeroDivisionError:
        print("Error: Division by zero is not allowed.")
    except Exception as e:
        print(f"An unexpected error occurred: {e}")
    else:
        print(f"The result of {a} divided by {b} is: {result}")

# Example:-
try:
    numerator = int(input("Enter the numerator: "))
    denominator = int(input("Enter the denominator: "))
    divide_numbers(numerator, denominator)
except ValueError:
    print("Error: Please enter valid numerical values.")
except Exception as e:
    print(f"An unexpected error occurred: {e}")

```

    Enter the numerator: a
    Error: Please enter valid numerical values.
    


```python
 "Explain the role of the finally keyword in exception handling. Write a code snippet to demonstrate its use."
def divide_numbers(a, b):
    try:
        result = a / b
        print(f"The result of {a} divided by {b} is: {result}")
    except ZeroDivisionError:
        print("Error: Division by zero is not allowed.")
    except Exception as e:
        print(f"An unexpected error occurred: {e}")
    finally:
        print("Finally block: This code will always be executed.")

# Example:-
try:
    numerator = int(input("Enter the numerator: "))
    denominator = int(input("Enter the denominator: "))
    divide_numbers(numerator, denominator)
except ValueError:
    print("Error: Please enter valid numerical values.")
except Exception as e:
    print(f"An unexpected error occurred: {e}")
finally:
    print("Outer Finally block: This code will always be executed, even if an exception occurred outside the function.")

```

    Enter the numerator: a
    Error: Please enter valid numerical values.
    Outer Finally block: This code will always be executed, even if an exception occurred outside the function.
    


```python
"Write a program that uses a try-except block to handle a FileNotFoundError."
try:
    file_path = "nonexistent_file.txt"  # Replace with the actual file path
    with open(file_path, 'r') as file:
        content = file.read()
        print("File Content:")
        print(content)
except FileNotFoundError:
    print(f"Error: File not found - {file_path}")
except Exception as e:
    print(f"An unexpected error occurred: {e}")

```

    Error: File not found - nonexistent_file.txt
    


```python
"Create a Python program that uses multiple except clauses to handle different types of exceptions."
def divide_numbers(a, b):
    try:
        result = a / b
        return result
    except ZeroDivisionError:
        print("Error: Division by zero is not allowed.")
    except TypeError:
        print("Error: Invalid data type for division.")
    except Exception as e:
        print(f"An unexpected error occurred: {e}")

# Example:-
try:
    numerator = int(input("Enter the numerator: "))
    denominator = int(input("Enter the denominator: "))
    result = divide_numbers(numerator, denominator)
    if result is not None:
        print(f"The result of {numerator} divided by {denominator} is: {result}")
except ValueError:
    print("Error: Please enter valid numerical values.")
except Exception as e:
    print(f"An unexpected error occurred: {e}")

```

    Enter the numerator: a
    Error: Please enter valid numerical values.
    


```python
"Implement a function that raises a custom exception if a given number is negative."
class NegativeNumberError(Exception):
    def __init__(self, value):
        self.value = value
        super().__init__(f"Negative number not allowed: {value}")

def check_positive_number(number):
    if number < 0:
        raise NegativeNumberError(number)
    else:
        print(f"The number {number} is positive.")

# Example usage:
try:
    check_positive_number(10)
    check_positive_number(-5)
except NegativeNumberError as e:
    print(f"Error: {e}")
   
```

    The number 10 is positive.
    Error: Negative number not allowed: -5
    


```python
"Write a function that uses the assert keyword to check if a given list is not empty."
def assert_not_empty(my_list):
    assert len(my_list) > 0, "The list is empty"
    print("The list is not empty")

# Example:-
my_list = [1, 2, 3]
assert_not_empty(my_list)

empty_list = []
assert_not_empty(empty_list)  # This will raise an AssertionError with the message "The list is empty"

```

    The list is not empty
    


    ---------------------------------------------------------------------------

    AssertionError                            Traceback (most recent call last)

    Cell In[12], line 11
          8 assert_not_empty(my_list)
         10 empty_list = []
    ---> 11 assert_not_empty(empty_list)
    

    Cell In[12], line 3, in assert_not_empty(my_list)
          2 def assert_not_empty(my_list):
    ----> 3     assert len(my_list) > 0, "The list is empty"
          4     print("The list is not empty")
    

    AssertionError: The list is empty



```python
"Develop a program that reads two numbers from the user and divides them. Handle different exceptions such as ZeroDivisionError and ValueError."
def divide_numbers():
    try:
        # Read two numbers from the user
        num1 = float(input("Enter the first number: "))
        num2 = float(input("Enter the second number: "))

        # Perform the division
        result = num1 / num2

        # Display the result
        print(f"The result of {num1} / {num2} is: {result}")

    except ValueError as ve:
        print(f"Error: {ve}. Please enter valid numbers.")
    except ZeroDivisionError:
        print("Error: Division by zero is not allowed.")
    except Exception as e:
        print(f"An unexpected error occurred: {e}")

if __name__ == "__main__":
    divide_numbers()
   
```

    Enter the first number: 1
    Enter the second number: 2
    The result of 1.0 / 2.0 is: 0.5
    


```python
"Write a function that takes a string as input and converts it to an integer. Handle the ValueError exception."
def string_to_integer(input_string):
    try:
        result = int(input_string)
        return result
    except ValueError:
        print("Error: Input is not a valid integer.")

# Example:-
input_str = "225"
result_int = string_to_integer(input_str)
print("Result:", result_int)

invalid_input_str = "abc"
result_invalid = string_to_integer(invalid_input_str)
# The function will print an error message, and you can handle it accordingly in your code.
   
```

    Result: 225
    Error: Input is not a valid integer.
    


```python
"Create a program that uses the try, except, else, and finally blocks to open a file, read its contents, and print them."
def read_file(file_path):
    try:
        # Try to open the file
        with open(file_path, 'r') as file:
            # Try to read the contents of the file
            content = file.read()

    except FileNotFoundError:
        print(f"Error: The file '{file_path}' does not exist.")
    except PermissionError:
        print(f"Error: Permission denied to open the file '{file_path}'.")
    except Exception as e:
        print(f"An unexpected error occurred: {e}")

    else:
        # If no exception occurred, print the file contents
        print(f"File contents:\n{content}")

    finally:
        # This block will always be executed, regardless of whether an exception occurred or not
        print("Finally block: This block is always executed.")

if __name__ == "__main__":
    file_path = input("Enter the file path: ")
    read_file(file_path)
   
```

    Enter the file path: C:\Users\HP\OneDrive\Desktop
    Error: Permission denied to open the file 'C:\Users\HP\OneDrive\Desktop'.
    Finally block: This block is always executed.
    


```python
"Define a custom exception class named CustomError. Write a program that raises this exception when a certain condition is met."
class CustomError(Exception):
    def __init__(self, message="A custom error occurred"):
        self.message = message
        super().__init__(self.message)

def check_condition(value):
    if value < 0:
        raise CustomError("The value cannot be negative")

# Example:-
try:
    user_input = int(input("Enter a non-negative number: "))
    check_condition(user_input)
    print("Input is valid:", user_input)
except CustomError as ce:
    print(f"CustomError: {ce}")
except ValueError:
    print("Error: Please enter a valid number.")
   
```

    Enter a non-negative number: 10
    Input is valid: 10
    


```python
"Implement a function that reads a file and prints its content. If the file is not found, raise a FileNotFoundError with a custom error message."
def read_and_print_file(file_path):
    try:
        with open(file_path, 'r') as file:
            content = file.read()
            print("File Content:")
            print(content)
    except FileNotFoundError:
        raise FileNotFoundError(f"Error: File not found - {file_path}")

# Example:-
try:
    file_path = "example.txt"  # Replace with the actual file path
    read_and_print_file(file_path)
except FileNotFoundError as e:
    print(e)
except Exception as e:
    print(f"An unexpected error occurred: {e}")
  
```

    Error: File not found - example.txt
    


```python
"Develop a program that uses the assert keyword to check if a given number is positive. If not, raise an AssertionError with a custom message."
def check_positive_number(number):
    assert number > 0, f"AssertionError: The number {number} is not positive."

# Example:-
try:
    user_input = int(input("Enter a positive number: "))
    check_positive_number(user_input)
    print(f"The number {user_input} is positive.")
except AssertionError as ae:
    print(ae)
except ValueError:
    print("Error: Please enter a valid number.")
   
```

    Enter a positive number: 5
    The number 5 is positive.
    


```python
"Create a function that calculates the square root of a positive number. Handle the ValueError exception if the user enters a negative number."
import math

def calculate_square_root(number):
    try:
        if number < 0:
            raise ValueError("Error: Cannot calculate the square root of a negative number.")
        result = math.sqrt(number)
        return result
    except ValueError as ve:
        raise ve

# Example:-
try:
    user_input = float(input("Enter a positive number: "))
    result = calculate_square_root(user_input)
    print(f"The square root of {user_input} is: {result}")
except ValueError as ve:
    print(ve)
except Exception as e:
    print(f"An unexpected error occurred: {e}")
   
```

    Enter a positive number: 20
    The square root of 20.0 is: 4.47213595499958
    


```python

```


```python

```


```python

```


```python

```


```python

```


```python

```


```python

```


```python

```


```python

```


```python

```


```python

```


```python

```


```python

```


```python

```
