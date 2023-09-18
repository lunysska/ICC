# Módulo 5. Tipos de datos, expresiones y flujo de control
## Semana 5

### Sesión 1. Ayudantía de Teoria
#### Tema: Expresiones con tipos de datos primitivos en Java
- Definición de expresión en Java.
- Clasificación de expresiones por su tipo de dato.
- Escritura de expresiones algebraicas: precedencia de los operadores y uso de paréntesis. Se sugiere a los estudiantes revisar el Cuadro 3.4 Operadores de Java, en Introducción a las Ciencias de la Computación con Java, de Elisa V. y Canek P., p. 92., como referencia para la precedencia de los 46 operadores en caso de consulta. Se exponen los ejemplos de la sección.
- Ejemplo con operadores lógicos (dinero, tienda1 y tienda2 son variables booleanas, se da una historia para contextualizar):
```java
dinero == true && tienda1 == true && tienda2 == true
```
y su diferencia con:
```java
dinero == true && ( tienda1 == true && tienda2 == true )
```
- Diferencia entre los operadores lógicos && y || con & y |.
- Operadores con el mismo nivel de precedencia se evalúan de izquierda a derecha, salvo los operadores de asignación.
- Ejemplos de evaluación de derecha a izquierda con operadores de asignación (=, +=, -=).  


### Sesión 2. Ayudantía de Teoria
#### Tema: Expresiones con error de incompatibilidad de tipos
- Ejemplos básicos de expresiones mal formadas que presentan error de incompatibilidad de tipos:  
- Ejemplo 1:  
```java
int a = 4, b = 2;
String saludo = "Hola";

b = saludo + a;
```
- Ejemplo 2:  
```java
int a = 4;
if(a = 4)
    System.out.println("a es igual a 4");
```
- Ejemplo 3:  
```java
double a = 3;
int b = 1;
b = a;
```

#### Tema: Casting de tipos primitivos
- Casting de ensanchamiento (widening casting). Definición y ejemplos.
```java
int distancia = 100;
double velocidad, tiempo = 6.0;

velocidad = distancia / tiempo;
```
- Casting de estrechamiento (narrowing casting). Definición y ejemplos.
```java
double masa = 500, volumen = 400000;
float densidad;

densidad = (float)(masa / volumen);
```
