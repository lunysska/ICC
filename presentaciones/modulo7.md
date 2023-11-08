## Semana 9

### Sesión 1. Ayudantía de Teoria
#### Tema: Cadenas en Java
- Se aplicó el [miniExamen1.pdf](../miniExamenes/miniExamen1.pdf)
- En Java, las cadenas de caracteres (o simplemente *cadenas*) son objetos de la clase *String*. Algunos métodos útiles de esta clase son:
- **int length()**: Devuelve un *int* con la longitud de la cadena.
- Ejemplo:
```java
    String saludo = "Hola mundo.";
    System.out.println(saludo.length());
```
- **String toUpperCase(), toLowerCase()**: Devuelven la cadena en mayúsculas o minúsculas, respectivamente.
- Ejemplo:
```java
    System.out.println(saludo.toUpperCase());
    System.out.println(saludo.toLowerCase());
```
- Nota: Con el código anterior no se modifica el contenido de la variable *saludo*. Para ello tendría que hacerse:
```java
    saludo = saludo.toUpperCase();
```
- **boolean equals(String)**: Devuelve *true* si las dos cadenas son iguales y *false* en caso contrario.
- Ejemplo:
```java
    String s1 = "rojo";
    String s2 = "azul";
    String s3 = "azul";
    System.out.println(s1.equals(s2));
    System.out.println(s2.equals(s3));
```
- Nota: Con este método, la comparación de la cadena "azul" con "AzUl" devolvería *false*. Para hacer la comparación ignorando mayúsculas y minúsculas, puede usarse el método **equalsIgnoreCase()**.
- **int compareTo(String)**: Devuelve 0 si ambas cadenas son iguales, un entero menor a cero si la primer cadena es lexicográficamente menor a la segunda, y un entero mayor a cero si la segunda cadena es lexicográficamente menor a la primera. El orden lexicográfico empleado es el de los caracteres del estándar Unicode.
- Ejemplo:
```java
    String saludo1 = "Hola mundo.";
    String saludo2 = "Buenos dias.";
    String saludo3 = "Hola mundo.";
    System.out.println(saludo1.compareTo(saludo2));
    System.out.println(saludo2.compareTo(saludo1));
    System.out.println(saludo1.compareTo(saludo3));
```
- Nota: Para hacer la comparación ignorando mayúsculas y minúsculas, puede usarse el método **compareToIgnoreCase()**.
- **char charAt(int)**: Devuelve el caracter ubicado en la posición indicada en la cadena.
- Ejemplo:
```java
    String saludo = "Hola mundo.";
    System.out.println(saludo.charAt(3));
```
-Nota: Los índices inician en 0, por lo que el código anterior imprime el caracter 'a'.

## Así queda el bosquejo de código que incluye las operaciones de manipulación para la colección estática.

```java
//import adecuado
public class PruebaProveedor{

public static void main( ..... ){

//1. Construir un objeto Proveedor
//Usuario: un nombre
String nombre = "costco";//lectura del teclado
Proveedor p = new Proveedor(nombre, 5);

//2. Agregar un producto para el
//proveedor "p"
Producto p1 = new Producto("pastel",
345.0,
'C',
new Fecha(31,8,2023));
p.agregaProducto(p1);

Producto p2 = new Producto("jabon",
45.0,
'A',
new Fecha(31,8,2023));
Producto p3 = new Producto("cuaderno",
60.0,
'E',
new Fecha(31,8,2023));

//3.Agregar dos productos más para el
//proveedor "p"
p.agregaProducto(p2);
p.agregaProducto(p3);

//4.
p.agregaProducto("computadora",
32,000.0,
'T',
31,8,2023);

//4'. Probando que el producto 4 se generó adecuadamente
//
System.out.println( p);
// <--- nombre y 4 productos

//variables al vuelo
System.out.println( p.recuperaProducto("computadora"));

//5. Modificando el precio del producto 4.
p.modificaPrecio("computadora", 16,000.0);

//6. Corroborando que el precio del producto sí se realizó
System.out.println( p);
System.out.println(p.recuperaProducto("computadora"));

}

}
```
