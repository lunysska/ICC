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
## Semana 8

### Sesión 2. Ayudantía de Teoria
#### Tema: Literales en Java (continuación)
[Dispositivas de la sesión](modulo5/diapositivasOctubre04.pdf)
- Literales de tipo *String*. Se especifican entre comillas dobles. Pueden incluir secuencias de escape y caracteres indicados con su código *Unicode* en *UTF-16* de 16 o 32 bits.
- Secuencias de escape comunes:

|Nombre|Representación|ASCII|
|--------|--------|--------|
|    Salto de línea    |    \n    | 10 |
|    Tabulación    |    \t    | 9 |
|    Comilla simple    |    \\'    | 39 |
|    Comillas dobles    |    \\"    | 34 |
|    Diagonal invertida    |    \\\    | 92 |
|    Caracter nulo    |    \0    | 0 |
- **Ejemplo 1**: Uso de secuencias de escape.
```java
public class Literales{

    public static void main(String[] args){
    
     String cadenaConSecuenciasDeEscape="\tTexto tabulado.\nComilla simple: \' \nComillas dobles: \" \nDiagonal invertida: \\ \nCaracter nulo: \0";
    
     System.out.println(cadenaConSecuenciasDeEscape);
     
    }

}
```
- **Ejemplo 2**: Impresión de emojis. En *UTF-16* (codificación empleada en Java) los emojis emplean códigos *Unicode* de dos bloques de 16 bits. Pueden expresarse con la sintaxis “\uxxxx\uxxxx”, donde cada *x* es un dígito hexadecimal.
```java
public class Literales{

    public static void main(String[] args){
    
     System.out.println("\uD83D\uDE00");     
     System.out.println("\uD83D\uDE01");
     System.out.println("\uD83D\uDE02");
     System.out.println("\uD83D\uDE03");
     System.out.println("\uD83D\uDE04");
     System.out.println("\uD83D\uDE05");
     System.out.println("\uD83D\uDE06");
     System.out.println("\uD83D\uDE07");
     System.out.println("\uD83D\uDE08");
     System.out.println("\uD83D\uDE09");
     
    }

}
```
- Literales booleanas. Sólo pueden tomar los valores *true* o *false* (verdadero o falso).
- **Ejemplo 1**:
```java
public class Literales{

    public static void main(String[] args){
    
     boolean b1 = true;
     boolean b2 = false;
     
     System.out.println(b1);
     System.out.println(b2);
     System.out.println(true);
          
    }

}
```
- Literal nula. Un objeto en Java puede inicializarse en *null*.
```java
public class Literales{

    int longitud;

    public static void main(String[] args){
    
     Literales l2 = null;
           
    }

}
```
- *null* es una literal que indica que la variable apunta a ningún objeto. Tratar de acceder a los atributos o métodos de un objeto nulo generará una excepción de puntero nulo (*NullPointerException*).
- **Ejemplo 1**:
```java
public class Literales{

    int longitud;

    public static void main(String[] args){
    
     Literales l2 = null;
     
     System.out.println(l2.longitud);
           
    }

}
```
- Al intentar compilar el código anterior se producirá un error "java.lang.NullPointerException".
#### Tema: Errores de incompatibilidad de tipos al invocar métodos
- Los errores de incompatibilidad de tipos también pueden producirse en expresiones que incluyen llamadas a métodos.
- **Ejemplo 1**: En la clase *RegistroMedico*, trabajada en sesiones anteriores, se tiene un método *getEstatura()* de tipo *double*:
```java
    public double getEstatura(){
        return estatura;
    }
```
- Si en la clase *PruebaRegistroMedico* se intenta hacer:
```java
public class PruebaRegistroMedico{

    public static void main(String[] args){
        
        RegistroMedico rm5 = new RegistroMedico("Laura","Altamira Quintanar",24,72.8,1.65);
        
        rm5.imprimeDetalles();
                
        int estaturaLaura = rm5.getEstatura();
        
    }

}
```
- Se producirá un error "incompatible types: possible lossy conversion from double to int". Esto se soluciona empleando una variable *double*:
```java
public class PruebaRegistroMedico{

    public static void main(String[] args){
        
        RegistroMedico rm5 = new RegistroMedico("Laura","Altamira Quintanar",24,72.8,1.65);
        
        rm5.imprimeDetalles();
                
        double estaturaLaura = rm5.getEstatura();
        System.out.println(estaturaLaura);
        
    }

}
```
- **Ejemplo 2**: En esta misma clase (*RegistroMedico*), obsérvese que se tiene un método getNombre() de tipo String y un método imprimeNombre() de tipo void.
```java
    public String getNombre(){
        return nombre;
    }
    
    public void imprimeNombre(){
        System.out.println(nombre);
    }
```
- Si en la clase *PruebaRegistroMedico* se hace:
```java
public class PruebaRegistroMedico{

    public static void main(String[] args){
        
        RegistroMedico rm5 = new RegistroMedico("Laura","Altamira Quintanar",24,72.8,1.65);
        
        rm5.imprimeDetalles();
                
        String nombreLaura = rm5.imprimeNombre();
        
    }

}
```
- Al intentar compilar se producirá un error "incompatible types: void cannot be converted to String". Basta con usar el método correcto para solucionar este error:
```java
public class PruebaRegistroMedico{

    public static void main(String[] args){
        
        RegistroMedico rm5 = new RegistroMedico("Laura","Altamira Quintanar",24,72.8,1.65);
        
        rm5.imprimeDetalles();
                
        String nombreLaura = rm5.getNombre();
        System.out.println(nombreLaura);
        
    }

}
```

