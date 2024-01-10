## Person class

```python
class Person:
    # Constructor method (called when an object is created)
    def __init__(self, name, age):
        self.name = name  # Attribute: Name of the person
        self.age = age    # Attribute: Age of the person

    # Method to greet
    def greet(self):
        return f"Hello, my name is {self.name} and I am {self.age} years old."

# Creating objects (instances) of the Person class
person1 = Person("Alice", 30)
person2 = Person("Bob", 25)

# Calling the greet method on objects
print(person1.greet())  # Output: Hello, my name is Alice and I am 30 years old.
print(person2.greet())  # Output: Hello, my name is Bob and I am 25 years old.
```


- We define a class called Person with a constructor (__init__) that takes name and age as parameters to initialize the attributes of the class.
- The greet method is defined within the class, which allows instances of the Person class to greet by returning a formatted message.
- We create two objects (person1 and person2) of the Person class and use them to call the greet method to print out personalized greetings.


## Class variables

```python
class Student:
    # Class variable to keep track of the number of students
    student_count = 0

    def __init__(self, name, grade):
        self.name = name
        self.grade = grade
        Student.student_count += 1  # Increment the class variable upon object creation

# Creating instances of the Student class
student1 = Student("Alice", "A")
student2 = Student("Bob", "B")

# Accessing the class variable
print(Student.student_count)  # Output: 2 (total number of students)

# Class variable can also be accessed using instances
print(student1.student_count)  # Output: 2
print(student2.student_count)  # Output: 2
```

Class variables in Python are variables shared among all instances of a class. They are declared within the class but outside of instance methods and have the same value across all objects created from that class. Class variables are typically used for data that should be consistent for all instances, such as configuration settings, constants, or shared counters.

## Instance variables

```python
class Person:
    def __init__(self, name, age):
        self.name = name      # Instance variable for name
        self.age = age        # Instance variable for age

    def introduce(self):
        return f"My name is {self.name}, and I am {self.age} years old."

# Creating instances of the Person class with unique instance variables
person1 = Person("Alice", 30)
person2 = Person("Bob", 25)

# Accessing instance variables
print(person1.name)  # Output: Alice
print(person2.age)   # Output: 25

# Calling instance method to access instance variables
print(person1.introduce())  # Output: My name is Alice, and I am 30 years old.
```

Instance variables in Python are variables that store data unique to each instance (object) of a class. They are defined within the class constructor (`__init__`) and represent the object's attributes or state. Each object has its own set of instance variables, allowing different objects of the same class to have different values for these variables. Instance variables are accessed and modified using the `self` parameter within instance methods.


## Class method

```python
class MyClass:
    class_variable = 0

    def __init__(self, value):
        self.value = value

    @classmethod
    def increment_class_variable(cls):
        cls.class_variable += 1

    def display(self):
        print(f"Value: {self.value}, Class Variable: {self.class_variable}")

# Creating instances of MyClass
obj1 = MyClass(10)
obj2 = MyClass(20)

# Using the class method to increment the class variable
MyClass.increment_class_variable()

obj1.display()  # Output: Value: 10, Class Variable: 1
obj2.display()  # Output: Value: 20, Class Variable: 1
```

Class methods in Python are functions defined within a class that operate on the class itself rather than instances. They are marked with the `@classmethod` decorator and take the class as their first parameter (usually named `cls`). Class methods can be used for operations related to the class, creating alternative constructors, accessing class-level attributes, and performing actions that affect the entire class.


## Instance method

```python
class Dog:
    def __init__(self, name, breed):
        self.name = name
        self.breed = breed
        self.energy_level = 100

    def bark(self):
        print(f"{self.name} (a {self.breed} dog) barks loudly!")

    def play(self, minutes):
        self.energy_level -= minutes * 2
        print(f"{self.name}'s energy level is now {self.energy_level}%")

# Creating instances of the Dog class
dog1 = Dog("Buddy", "Golden Retriever")
dog2 = Dog("Max", "Labrador")

# Calling instance methods on the instances
dog1.bark()             # Output: Buddy (a Golden Retriever dog) barks loudly!
dog1.play(15)           # Output: Buddy's energy level is now 70%

dog2.bark()             # Output: Max (a Labrador dog) barks loudly!
dog2.play(10)           # Output: Max's energy level is now 80%
```

Instance methods in Python are functions defined within a class that operate on instance-specific data. They take the instance itself as their first parameter (usually named self) and can access and modify object-specific attributes. Instance methods encapsulate the behavior of individual objects and are called on instances of the class to perform object-specific actions.
