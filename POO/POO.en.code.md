# POO | en | code

examples of each of the Object-Oriented Programming (OOP) principles in Python, along with a brief explanation for each

## Encapsulation

Encapsulation is the concept of hiding the internal details of an object and exposing only what is necessary. In Python, private attributes can be created using double underscores (`__`). This protects the data of an object and prevents direct access from outside the class.

```python
class Rectangle:
    def __init__(self, width, height):
        self.__width = width  # Private attribute
        self.__height = height  # Private attribute

    def get_area(self):
        return self.__width * self.__height

    def get_perimeter(self):
        return 2 * (self.__width + self.__height)

# Creating a Rectangle object
my_rectangle = Rectangle(5, 3)
print("Area:", my_rectangle.get_area())  # Access through methods
print("Perimeter:", my_rectangle.get_perimeter())
```

## Inheritance

Inheritance is a mechanism that allows creating a new class based on an existing class, inheriting its attributes and methods. In the following example, the `Square` class inherits from the `Rectangle` class.

```python
class Square(Rectangle):
    def __init__(self, side):
        super().__init__(side, side)  # Calls the constructor of the base class

# Creating a Square object (subclass of Rectangle)
my_square = Square(4)
print("Area of the square:", my_square.get_area())
print("Perimeter of the square:", my_square.get_perimeter())
```

## Polymorphism

Polymorphism allows objects of different classes to behave similarly through a common interface. In this example, the `print_area` function can receive objects of different classes that implement the `get_area` method.

```python
def print_area(shape):
    print("Area:", shape.get_area())

# Calling print_area with different objects
print_area(my_rectangle)  # Calls the method of Rectangle
print_area(my_square)  # Calls the method of Square (which inherits from Rectangle)
```

## Abstraction

Abstraction is the process of simplifying an object by focusing on its most important features and omitting unnecessary details. The `GeometricShape` class defines a `get_area` method as an abstraction of a generic geometric shape. Subclasses, like `Triangle`, provide concrete implementations of this method.

```python
class GeometricShape:
    def get_area(self):
        pass  # Implementation is left to subclasses

class Triangle(GeometricShape):
    def __init__(self, base, height):
        self.base = base
        self.height = height

    def get_area(self):
        return (self.base * self.height) / 2

# Using abstraction with the GeometricShape class
my_triangle = Triangle(4, 6)
print("Area of the triangle:", my_triangle.get_area())
```

I hope these examples clarify the Object-Oriented Programming principles in Python for you!
