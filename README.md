# python-py
# Python Basics - Chapter 1 Solutions

#.1 Print Formatting
print(f"My name is Blackie.")
print(f"I am {25} years old.")
print(f"I love Python programming!")

# 2 Swapping Variables
a, b = 5, 10
a, b = b, a
print(f"After swapping: a = {a}, b = {b}")

#.3 Simple Calculator
def calculator(num1, num2, operator):
    if operator == '+':
        return num1 + num2
    elif operator == '-':
        return num1 - num2
    elif operator == '*':
        return num1 * num2
    elif operator == '/':
        return num1 / num2 if num2 != 0 else "Cannot divide by zero"
    else:
        return "Invalid operator"
print(calculator(10, 5, '+'))

# 4. Type Checking
x = 10
y = 3.14
z = "HUCISA"
a = True
print(type(x), type(y), type(z), type(a))

# 5. List Operations
numbers = [2, 4, 6, 8, 10]
numbers.append(12)
numbers.remove(4)
print(f"Max: {max(numbers)}, Min: {min(numbers)}")

# 6. Dictionary Manipulation
students = {"Alice": 20, "Bob": 22}
students["Charlie"] = 23
students["Alice"] = 21
del students["Bob"]
print(students)

# 7. Tuple Unpacking
tuple_data = (10, 20, 30)
a, b, c = tuple_data
print(a, b, c)

# 9. Sum of Even Numbers
sum_even = sum(i for i in range(1, 101) if i % 2 == 0)
print(sum_even)

# 8. Factorial Calculation
def factorial(n):
    result = 1
    for i in range(1, n + 1):
        result *= i
    return result
print(factorial(5))

# 10. Multiplication Table
def multiplication_table(n):
    for i in range(1, 11):
        print(f"{n} x {i} = {n * i}")
multiplication_table(7)

# 12. Reverse a String Using Loop
def reverse_string(s):
    reversed_s = ""
    for char in s:
        reversed_s = char + reversed_s
    return reversed_s
print(reverse_string("Python"))

# 13. Fibonacci Sequence
def fibonacci(n):
    sequence = [0, 1]
    for _ in range(n - 2):
        sequence.append(sequence[-1] + sequence[-2])
    return sequence[:n]
print(fibonacci(10))

# 14. Count Digits in a Number
def count_digits(n):
    return len(str(abs(n)))
print(count_digits(12345))

# 15. Prime Number Check
def is_prime(n):
    if n < 2:
        return False
    for i in range(2, int(n**0.5) + 1):
        if n % i == 0:
            return False
    return True
print(is_prime(29))

# 16.Finding Common Elements
list1 = [1, 2, 3, 4, 5]
list2 = [3, 4, 5, 6, 7]
common_elements = list(set(list1) & set(list2))
print(common_elements)

# 17. Object-Oriented Programming
class Student:
    def __init__(self, name, age, course):
        self.name = name
        self.age = age
        self.course = course
    def display_info(self):
        print(f"Name: {self.name}, Age: {self.age}, Course: {self.course}")
student1 = Student("Alice", 20, "CS")
student1.display_info()

# 18. Inheritance
class Course:
    def get_details(self):
        return "General Course"
class WebDevClass(Course):
    def get_details(self):
        return "Web Development Course"
course = WebDevClass()
print(course.get_details())

# 19. Encapsulation
class BankAccount:
    def __init__(self, balance=0):
        self.__balance = balance
    def deposit(self, amount):
        self.__balance += amount
    def withdraw(self, amount):
        if amount <= self.__balance:
            self.__balance -= amount
        else:
            print("Insufficient funds")
    def get_balance(self):
        return self.__balance
account = BankAccount(1000)
account.deposit(500)
print(account.get_balance())

# 19. Polymorphism
class Car:
    def move(self):
        print("The car is moving fast")
class Bike:
    def move(self):
        print("The bike is moving slowly")
def transport_movement(vehicle):
    vehicle.move()
car = Car()
bike = Bike()
transport_movement(car)
transport_movement(bike)

# 20. Method Overloading (Using Default Arguments)
class MathOperations:
    def add(self, a, b, c=0):
        return a + b + c
math_op = MathOperations()
print(math_op.add(2, 3))
print(math_op.add(2, 3, 5))
