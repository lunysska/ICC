# Módulo 4. Clases y objetos en Java
## Semana 4

### Sesión 1. Teoria
#### Tema: Clases en Java
- Uso de la palabra reservada **class**
- Convenciones para el nombrado de clases
- bloque de clases

#### Tema: Atributos de la clase
- el *;* es el fin de la expresión
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
- Esta tipo de metodología es la que se usará en el curso

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
- Propuesta básica de clase Producto. Generar un archivo *Producto.java*
  
```java
class Producto {
    String nombre;
    float precio;
    char tipo;
}
```
#### Tema: el método main
- Clase de pruebas.
- Se debe crear una clase de pruebas para cada prueba de clase a realizar.
- Generar el archivo: *PruebaProducto.java*
- El método *main*
  
```java
class PruebaProducto {
    public static void main( String args[]){
    }
}
```

#### Tema: creando objetos en Java
- el uso de el operador *new*
```java
class PruebaProducto {
    public static void main( String args[]){
        Producto producto1 = new Producto();
    }
}
```

 #### Tema: el operador *.*
- asignando valores a los atributos del objeto
```java
class PruebaProducto {
    public static void main( String args[]){
        Producto producto1 = new Producto();
        producto1.nombre = "borrador";
        producto1.precio = 12.45;
        producto1.tipo = 'P';
    }
}
```

#### Tema: comunicación con la salida estandar.
- *System.out.println()*
- concatenando cadenas para el formato de la salida estandar
```java
class PruebaProducto {
    public static void main( String args[]){
        Producto producto1 = new Producto();
        producto1.nombre = "borrador";
        producto1.precio = 12.45;
        producto1.tipo = 'P';
        System.out.println("El nombre es:"+producto1.nombre);
        System.out.println("El precio es:"+producto1.precio);
        System.out.println("El tipo es:"+producto1.tipo);
    }
}
``` 
