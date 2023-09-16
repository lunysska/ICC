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

#### Ejemplos vistos en la Ayudantía de Teoría

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
(Alternativamente podrían ser x1, y1, x2, y2)  
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

### Sesion 2. Ayudantía Teoría

  1. Ver de manera general una introducción a tipos de datos, para poder usarlos de manera general en diferentes clases básicas de Java.
  2. Ver de manera muy general el concepto de expresiones, para poderlas usar de forma general en la definición de clases básicas en Java.
  3. Mostrar otros ejemplos de clases donde usen atributos de tipos variados y menos comunes de uso. Y donde empiecen a usar algunas expresiones que usen algunos operadores básicos.

## Semana 4
### Sesión 1. Teoría
#### Tema: Encapsulacion 
- concepto teórico
- en código:
```java
private
public
```
- El acceso a atributos se restringe cuando se  cambian a private
- pero como aun se tiene que poder modificar los valores de los atributos, se busca algun otro mecanismo para lograrlo. Y se logra por medio de un metodo.
```java
public void  setAtributo(tipoDeAtributo valor{ atributo = valor }
```
- el nombrado de los metodos es una convencion, no error sintactico.
- se conocen como setters o metodos de modificacion
- de esta manera se logra ese codigo
```java
class Producto {
    private String nombre;
    private float precio;
    private char tipo;

    public void  setNombre(String n){
        nombre = valor;
    }
    public void  setPrecio(String p){
        precio = p;
    }
    public void  setTipo(char t){
        tipo = t;
    }
}
```
- por supuesto la clase de prueba tiene que cambiar, ya que la manera en que estaba funcionando en la versión anterior, ahora ya no funcionaría.
- ¿cómo quedaria?

#### Tema: Comunicación con la salida estándar en un método. 
* ahora la comunicacion a la pantalla tampoco se logra como se tenia, pues el acceso de los atributos se encuentra restringido.
* Una manera de hacerlo, con mejor diseño, es hacer un método que haga este proceso.
```java
public void imprimirDetalles(){
        System.out.println("El nombre es:"+nombre);
        System.out.println("El precio es:"+.precio);
        System.out.println("El tipo es:"+.tipo);
}
```
- por supuesto también debe cambiar la clase prueba para que funcione con estos cambios.
- ¿cómo quedaria?
