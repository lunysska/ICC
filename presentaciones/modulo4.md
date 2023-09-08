# Módulo 4. Clases y objetos en Java
## Semana 4

### Sesión 1. Teoria
#### Tema: Clases en Java
- Uso de la palabra reservada **class**
- Convenciones para el nombrado de clases
- bloque de clases

#### Tema: Atributos de la clase

- tipos de datos, qué son, para qué sirven.
- lenguajes de programación tipificados, no-tipificados (qué pasa con el manejo de la memoria).
- tipos de datos en Java: tipos de datos primitivos y clases
- ejemplos de construcción de clase con atributos primitivos:
```java
class Perro {
    int edad;
    char sexo;
    float peso;
}
```

#### Tema: Metodologías de programación
- Seguimiento a metodologías ágiles de programación

### Sesion 2. Ayudantía Teoría
Más ejemplos de definición de clases, en diseño, con atributos primitivos, podría ser la continuación de la clase Polinomio, y así

### Ejemplos vistos en la Ayudantía de Teoría

Ejemplo 1: Clase Vector2D
Atributos:  
    -- x: double  
    -- y: double  
Métodos:  
    \+ norma(): double  
    \+ anguloRadianes(): double  
    \+ anguloGrados(): double  
    \+ ortogonal(v: Vector2D): bool  
    \+ suma(v: Vector2D): Vector2D  
    \+ productoPunto(v: Vector2D): double  
    \+ resta(v: Vector2D): Vector2D  
    \+ productorPorEscalar(a: double): Vector2D  
  
Ejemplo 2: Clase Ventana  
Atributos:  
    -- x: int    
    -- y: int  
    -- l: int  
    -- h: int  
(Alternativamente podrían ser x_1, y_1, x_2, y_2)  
Métodos:  
    \+ agrandar(p: int, q: int)  
    \+ pantallaCompleta()  
    \+ minimizar()  
    \+priorizar()  
    \+mover()  
    \+cerrar()  
     

### Sesion 2. Teoría

#### Tema: String no es un tipo básico. Es una clase
#### Tema: Presentación del sistema de semestre
- Inventario
- Qué clase es la más básica: Producto
- Propuesta básica de clase Producto:
  
```java
Archivo: Producto.java
class Producto {
    String nombre;
    float precio;
    char tipo;
}
```
###
