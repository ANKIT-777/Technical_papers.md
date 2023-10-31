# SOLID PROPERTIES ->>>>>>
- SOLID is an acronym that represents a set of five design principles in object-oriented programming that aim to create more maintainable, scalable, and understandable software.
  
**Single Responsibility Principle (SRP):**
1. **Definition**: A class should have only one reason to change, meaning it should have a single responsibility.

```python
class ErrorLogger:
    def log_error(self, message):
        # Log error to a file
        pass

class UserManager:
    def register_user(self, username, password):
        # Register a new user
        pass
```

**Open/Closed Principle (OCP):**
1. **Definition**: Software entities should be open for extension but closed for modification. New functionality should be added without changing existing code.

```python
class Shape(ABC):
    @abstractmethod
    def area(self):
        pass

class Circle(Shape):
    def __init__(self, radius):
        self.radius = radius

    def area(self):
        return 3.14 * self.radius ** 2

class Rectangle(Shape):
    def __init__(self, width, height):
        self.width = width
        self.height = height

    def area(self):
        return self.width * self.height
```

**Liskov Substitution Principle (LSP):**
1. **Definition**: Subtypes must be substitutable for their base types without altering program correctness.

```python
class Bird(ABC):
    @abstractmethod
    def speak(self):
        pass

class Duck(Bird):
    def speak(self):
        return "Quack"

class Parrot(Bird):
    def speak(self):
        return "Polly wants a cracker"
```

**Interface Segregation Principle (ISP):**
1. **Definition**: Clients should not be forced to depend on interfaces they don't use. Create focused interfaces.


```python
class Authenticatable(ABC):
    @abstractmethod
    def login(self, username, password):
        pass

class ProfileManageable(ABC):
    @abstractmethod
    def update_profile(self, data):
        pass

class User(Authenticatable, ProfileManageable):
    def login(self, username, password):
        pass

    def update_profile(self, data):
        pass
```

**Dependency Inversion Principle (DIP):**
1. **Definition**: High-level modules should not depend on low-level modules; both should depend on abstractions.

```python
class DatabaseConnection(ABC):
    @abstractmethod
    def execute_query(self, query):
        pass

class MySQLConnection(DatabaseConnection):
    def execute_query(self, query):
        # Execute MySQL query
        pass

class PostgreSQLConnection(DatabaseConnection):
    def execute_query(self, query):
        # Execute PostgreSQL query
        pass
```
