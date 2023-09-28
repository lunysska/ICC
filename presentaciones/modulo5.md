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

## Semana 7

### Sesión 2. Ayudantía de Teoria
#### Tema: Diferencia entre sentencias, expresiones y literales en Java
- Definición y ejemplos de sentencias, expresiones y literales.
- **Sentencia**: Unidad mínima funcional de código. Suelen terminar en punto y coma (aunque no siempre es el caso).
- **Expresión**: Combinación de literales, variables, operadores y/o llamadas a métodos que devuelve un valor.
- **Literal**: Representación explícita de un valor en el código.
#### Tema: Uso de prefijos y sufijos en literales
- Literales de tipo numérico entero. En Java estas literales se asumen de tipo *int*. Para indicar una literal entera de tipo *long* se usa el sufijo *l* (ele).
- Ejemplo:
```java
     System.out.println(1000000000000);
```
- El código anterior marcará error al compilar (error: integer number too large). Para solucionar esto se agrega el sufijo *l*:
```java
     System.out.println(1000000000000l);
```
- Ejemplo:
```java
     System.out.println(1000000*1000000);
```
- El código anterior imprimirá **-727379968**, debido a un error de desbordamiento. Para solucionar esto se agrega el sufijo *l*:
```java
     System.out.println(1000000l*1000000l);
```
- Con esto ya se obtiene el resultado deseado: **1000000000000**.
- También pueden agregarse prefijos a las literales enteras para usar binario, octal o hexadecimal en su representación:

|Base|Prefijo|Ejemplo|Valor en decimal|
|--------|--------|--------|--------|
|    Binario    |    0b o 0B    | 0b111 | 7 |
|    Octal    |    0    | 0127 | 87 |
|    Hexadecimal    |    0x o 0X    | 0xaf1 | 2801 |

- Literales de tipo numérico de punto flotante. En Java estas literales se asumen de tipo *double*. Para indicar una literal entera de tipo *float* se usa el sufijo *f*. Adicionalmente puede agregarse el sufijo *d* para indicar explícitamente el tipo double (aunque esto no es necesario).
-  Ejemplos:
```java
     float f1 = 3.14f;
     double d1 = 20d;
```
- También puede usarse notación científica:
```java
     float f2 = 1e-6f;
     double d2 = 1e6;
```
- Literales de tipo *char* (caracter). En Java existen tres formas de representar estas literales:
- **Forma 1**: Con el caracter entre comillas simples.
- Ejemplo:
```java
     char c1 = 'a';
```
- También pueden emplearse secuencias de escape. Por ejemplo, para un salto de línea:
```java
     char c2 = '\n';
```
- **Forma 2**: Con un entero (octal, decimal o hexadecimal) en el intervalo 0 a 65535 (entero sin signo de 16 bits = 2 bytes).
-  Ejemplo (caracter 'A'):
```java
     char c3 = 65;
```
- **Forma 3**: Con el código *Unicode* asociado al caracter en el formato **\uxxxx**, donde **xxxx** son cuatro dígitos hexadecimales.
- Ejemplo (caracter de derechos reservados '©'):
```java
     char c4 = '\u00a9';
```
