# OOps in python ----->

1. **Classes and Objects**:
   - Classes are blueprints for creating objects.
   - Objects are instances of classes.
   ```python
   class Car:
       pass  # Class 

   my_car = Car()  # Object 
   ```

2. **Attributes**:
   - Attributes are variables that store data specific to an object.
   ```python
   class Car:
       make = "Toyota"  # Class attribute
       def __init__(self, model):
           self.model = model  # Instance attribute

   my_car = Car("Camry")
   print(my_car.make)    # Access class attribute
   print(my_car.model)   # Access instance attribute
   ```

3. **Methods**:
   - Methods are functions defined inside a class to perform actions.
   ```python
   class Dog:
       def bark(self):
           return "Woof!"

   my_dog = Dog()
   print(my_dog.bark())  # Call the method
   ```

4. **Constructor (`__init__`)**:
   - The `__init__` method initializes object attributes when an object is created.
   ```python
   class Person:
       def __init__(self, name, age):
           self.name = name
           self.age = age

   person1 = Person("Alice", 30)
   ```

5. **Inheritance**:
   - Inheritance allows a subclass to inherit attributes and methods from a superclass.
   ```python
   class Animal:
       def speak(self):
           pass  # Base class method

   class Dog(Animal):
       def speak(self):
           return "Woof!"  # Subclass method

   my_dog = Dog()
   print(my_dog.speak())  # Calls the subclass method
   ```

6. **Polymorphism**:
   - Polymorphism allows different classes to be treated as instances of a common superclass.
   ```python
   def animal_sound(animal):
       return animal.speak()

   dog = Dog()
   cat = Cat()
   print(animal_sound(dog))  # Dynamic method invocation
   ```

7. **Abstraction**:
   - Abstraction simplifies complex reality by modeling classes based on essential properties and behaviors.
   ```python
   from abc import ABC, abstractmethod

   class Shape(ABC):
       @abstractmethod
       def area(self):
           pass

   class Circle(Shape):
       def area(self):
           return 3.14 * self.radius
   ```

8. **Access Control**:
   - Python uses naming conventions for access control (`_protected, __private`).
   ```python
   class MyClass:
       def __init__(self):
           self.public_var = "Public"
           self._protected_var = "Protected"
           self.__private_var = "Private"

   obj = MyClass()
   print(obj.public_var)
   print(obj._protected_var)
   # print(obj.__private_var)  # Error, private variable not accessible
   ```
