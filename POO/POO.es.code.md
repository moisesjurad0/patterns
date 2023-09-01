# POO | es | code

ejemplos de código en Python que ilustran cada uno de los pilares de la Programación Orientada a Objetos (POO).

## Encapsulación

En este ejemplo, los atributos `ancho` y `alto` están encapsulados como atributos privados utilizando doble guion bajo (`__`). Los métodos `obtener_area` y `obtener_perimetro` proporcionan acceso controlado a estos atributos.

```python
class Rectangulo:
    def __init__(self, ancho, alto):
        self.__ancho = ancho  # Atributo privado
        self.__alto = alto    # Atributo privado

    def obtener_area(self):
        return self.__ancho * self.__alto

    def obtener_perimetro(self):
        return 2 * (self.__ancho + self.__alto)

# Creación de un objeto Rectangulo
mi_rectangulo = Rectangulo(5, 3)
print("Área:", mi_rectangulo.obtener_area())  # Acceso a través de métodos
print("Perímetro:", mi_rectangulo.obtener_perimetro())
```

## Herencia

La clase `Cuadrado` hereda de la clase `Rectangulo`, lo que significa que obtiene sus atributos y métodos. Esto demuestra el concepto de herencia.

```python
class Cuadrado(Rectangulo):
    def __init__(self, lado):
        super().__init__(lado, lado)  # Llama al constructor de la clase base

# Creación de un objeto Cuadrado (subclase de Rectangulo)
mi_cuadrado = Cuadrado(4)
print("Área del cuadrado:", mi_cuadrado.obtener_area())
print("Perímetro del cuadrado:", mi_cuadrado.obtener_perimetro())
```

## Polimorfismo

La función `imprimir_area` puede recibir objetos de diferentes clases que implementan el método `obtener_area`. Esto es un ejemplo de polimorfismo.

```python
def imprimir_area(figura):
    print("Área:", figura.obtener_area())

# Llamada a imprimir_area con diferentes objetos
imprimir_area(mi_rectangulo)  # Llama al método de Rectangulo
imprimir_area(mi_cuadrado)   # Llama al método de Cuadrado (que hereda de Rectangulo)
```

## Abstracción

La clase `FiguraGeometrica` define un método `obtener_area` como una abstracción de una figura geométrica genérica. Las subclases como `Triangulo` proporcionan implementaciones concretas de este método.

```python
class FiguraGeometrica:
    def obtener_area(self):
        pass  # Dejamos la implementación a las subclases

class Triangulo(FiguraGeometrica):
    def __init__(self, base, altura):
        self.base = base
        self.altura = altura

    def obtener_area(self):
        return (self.base * self.altura) / 2

# Uso de abstracción con la clase FiguraGeometrica
mi_triangulo = Triangulo(4, 6)
print("Área del triángulo:", mi_triangulo.obtener_area())
```
