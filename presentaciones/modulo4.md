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

## Semana 5
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

## Semana 6
### Sesión 1. Ayudantía de Teoría
#### Tema: Encapsulacion
- Ejemplo: clase RegistroMedico, que registrará el perfil médico de un paciente en un consultorio. Por sencillez se consideran solo cinco atributos.

```java
class RegistroMedico{
    private String nombre, apellidos;
    private int edad, peso;
    private double estatura;
}  
```
- Se usará una clase PruebaRegistroMedico para hacer las pruebas. ¿Qué ocurre con lo siguiente al intentar compilar?
```java
public class PruebaRegistroMedico{

    public static void main(String[] args){
    
        RegistroMedico rm = new RegistroMedico();        
        rm.edad = 20;

     }
}
```
- Se producirá un error: PruebaRegistroMedico.java:15: error: edad has private access in RegistroMedico.
- Se modifica la clase RegistroMedico con un setter.
```java
    public void setEdad(int e){
        edad = e;
    }
```
- Ahora se puede hacer:
```java
        rm.setEdad(20);
```
- Pero si se hace lo siguiente:
```java
        System.out.println(rm.edad);
```
- Se producirá un error nuevamente: PruebaRegistroMedico.java:26: error: edad has private access in RegistroMedico.
- Se verán 3 formas diferentes de manejarlo.
- Forma 1: Con un getter.
```java
    public int getEdad(){
        return edad;
    }
```
- Ahora puede hacerse:
```java
        System.out.println(rm.getEdad());
```
- Forma 2: Con un método para imprimir la edad.
```java
    public void imprimeEdad(){
        System.out.println(edad);
    }
```
- Ahora puede hacerse:
```java
        rm.imprimeEdad();
```
- Forma 3: Usando el getter y guardando la edad en una variable auxiliar.
```java
        int edad1;
        edad1 = rm.getEdad();
        System.out.println(edad1);
```
- Se agregan a la clase RegistroMedico setters y un método para mostrar todos los atributos:
```java
    public void setNombre(String n){
        nombre = n;
    }
    
    public void setApellidos(String a){
        apellidos = a;
    }

    public void setPeso(int p){
        peso = p;
    }
    
    public void setEstatura(double e){
        estatura = e;
    }
    
    public void imprimeDetalles(){
        System.out.println("Nombre: "+nombre);
        System.out.println("Apellidos: "+apellidos);
        System.out.println("Edad: "+edad);
        System.out.println("Peso: "+peso);
        System.out.println("Estatura: "+estatura);
    }    
```
- Se prueba el funcionamiento con lo siguiente en la clase PruebaRegistroMedico:
```java
        rm.setNombre("Mario");        
        rm.setApellidos("Moncayo Tapia");
        rm.setPeso(70);
        rm.setEstatura(1.70);

        rm.imprimeDetalles();
```
- Se observa que la estatura se imprime como "Estatura: 1.7". ¿Cómo especificar el número de digitos después del punto?
- Uso de System.out.printf.
```java
    public void imprimeEstatura(){
        System.out.printf("Estatura: %.2f \n",estatura);
    }
```
- Se puede probar ahora haciendo:
```java
        rm.imprimeEstatura();
```

### Sesión 1. Teoría
#### Tema: Hoy vi metodos constructores
#### Tema: El operador new y el manejo de memoria
#### Tema: Coml se define el stack y el heap
#### Tema: Muchos objetos de una misma clase y sus respectivos espacios en memoria
#### Tema: Modificacion de los.valores de atributos con el.operador punto
#### Tema: Repasamos la firma de un metodo. Para mejorar la intro
#### Tema: El constructor por omision y su perdida
#### Tema: Y vimos diferentes constructores por sustitucion, es decir, uno sustituye al otro

### Sesión 2. Ayudantía de Teoría
#### Tema: El método printf
- Sintaxis:  
> **System.out.printf("Cadena a formatear",argumentos);**  

Los *argumentos* son literales o variables, que van asociados con *especificadores de formato* incluidos en la *cadena a formatear* . Por ejemplo, en el código de la sesión anterior:
```java
    public void imprimeEstatura(){
        System.out.printf("Estatura: %.2f \n",estatura);
    }
```

- Se tiene el *especificador de formato* **%.2f**, que indica el formato que se le dará a la variable *estatura* (un *double* que será mostrado con dos decimales después del punto).  
- Sintaxis de los *especificadores de formato*:
> **%\<banderas>\<ancho>\<.precisión>[caracter de conversión]**  

En la expresión anterior, *banderas*, *ancho* y *.precisión* son opcionales.

- Banderas más comunes:

|Bandera|Función|
|--------|--------|
|    -    |    Justificar a la izquierda    |
|    +    |    Imprimir signo (- o +), para valores numéricos    |
|    0    |    Llenar el ancho con ceros a la izquierda, para valores numéricos    |
|    ,    |    Incluir las *comas de los miles* en valores numéricos    |
|    espacio (' ')    |    Imprimir el signo - en números negativos y un espacio previo en positivos, para valores numéricos.    |

- Caracteres de conversión más comunes:

|Caracter|Uso|
|--------|--------|
|    d    |    Enteros decimales (byte, short, int, long)    |
|    f    |    Números de punto flotante (float, double)    |
|    c    |    Caracter, C para pasar a mayúscula (char)    |
|    s    |    String, S para pasar la cadena completa a mayúsculas    |
|    n    |    Salto de línea (específico de la plataforma)    |
- Ejemplo: Implementar un método en la clase RegistroMedico para imprimir el nombre completo (nombre y apellidos) en mayúsculas, incluyendo el salto de línea.
- Solución:
```java
    public void imprimeNombreCompletoMayusculas(){
        System.out.printf("%S %S%n",nombre,apellidos);
    }
```
#### Tema: Constructores
- Ejemplo: constructor básico para la clase RegistroMedico.
```java
    public RegistroMedico(String n, String a, int e, int p, double es){
        nombre = n;
        apellidos = a;
        edad = e;
        peso = p;
        estatura = es;
    }
```
- En la clase PruebaRegistroMedico podemos ahora crear un nuevo objeto como:
```java
        RegistroMedico rm2 = new RegistroMedico("Arturo","Benavides Gama",21,80,1.75);
```
- Consideremos ahora un atributo adicional *IMC* (Índice de Masa Corporal) en nuestra clase RegistroMedico:
```java
    double IMC;
```
- Por definición se tiene que:  
$IMC = peso / estatura^2$  
- Se modifica el constructor para que inicialice el *IMC* adecuadamente:
```java
    public RegistroMedico(String n, String a, int e, int p, double es){
        nombre = n;
        apellidos = a;
        edad = e;
        peso = p;
        estatura = es;
        IMC = peso / (estatura*estatura);
    }
```
- Se observa que en la sentencia que calcula el *IMC* se está empleando un casting implícito.

### Sesión 2. Teoría
#### Tema:Varias formas de crear objetos en una misma clase
```java
public Producto( string n, float p, char t){
    nombre = n;
    precio = p;
    tipo = t;
}
```

#### Tema: El constructor por omision
#### Tema: Metodos
- Que son
- Su firma
- El identificador unico
- Los argumentos
- Tipos de metodos: constructores,  setters, getters, de control, auxiliares
- La sobrecarga de metodos
- el valor de retorno de un método

## Semana 7
### Sesión 1. Ayudantía de Teoría
#### Tema: El método printf
- **Ejemplo**: Definir un método en la clase RegistroMedico que imprima el nombre completo con el siguiente formato:  
<pre>
Nombre:               &lt;Nombre&gt;
Apellidos:         &lt;Apellidos&gt;
</pre>
donde se imprime el texto en un espacio de exactamente 30 caracteres de ancho.
- Primera aproximación (código en RegistroMedico):
```java
    public void imprimeNombreCompleto30Espacios(){
        System.out.printf("Nombre: %22s%n",nombre);
        System.out.printf("Apellidos: %19s%n",apellidos);
    }
```
- Sin embargo, con este código se presentará un problema con nombres o apellidos demasiado largos: se excederá el espacio de 30 caracteres (el ancho indicado es un mínimo). Solución: usar la precisión, que en *Strings* indica longitud máxima de impresión.
```java
    public void imprimeNombreCompleto30Espacios(){
        System.out.printf("Nombre: %22.22s%n",nombre);
        System.out.printf("Apellidos: %19.19s%n",apellidos);
    }
```
- Con este código se cortará la impresión cuando se haya alcanzado el máximo de caracteres, por lo que se asegura que el texto ocupará exactamente 30 caracteres.
#### Tema: Sobrecarga de constructores
- **Ejemplo**: Definir un constructor adicional en la clase RegistroMedico que reciba únicamente como parámetros el nombre y apellidos.
```java
    public RegistroMedico(String n, String a){
        nombre = n;
        apellidos = a;
    }
```
- Al generar un objeto (códgio en PruebaRegistroMedico):
```java
        RegistroMedico rm4 = new RegistroMedico("Pablo","Lara Guzman");
```
el resto de los atributos tendrán inicialmente sus valores por defecto (que es 0 en el caso de tipos primitivos numéricos).
- **Ejemplo**: Definir un constructor adicional en la clase RegistroMedico que reciba el mismo número de parámetros que el primer constructor definido, pero donde el peso recibido sea de tipo double.
```java
    public RegistroMedico(String n, String a, int e, double p, double es){
        nombre = n;
        apellidos = a;
        edad = e;
        peso = (int)p;
        estatura = es;
        IMC = peso / (estatura*estatura);
    }
```
-**Observación**: Al hacer el casting para pasar el peso a *int*, el valor se trunca. Para redondear al entero más cercano puede hacerse en su lugar:
```java
        peso = (int)(Math.round(p));
```
donde se usa el método *Math.round()*.
- Puede ahora generarse un objeto de tipo *RegistroMedico* enviando como parámetro un *double* para el peso (código en PruebaRegistroMedico):
```java
        RegistroMedico rm5 = new RegistroMedico("Laura","Altamira Quintanar",24,72.8,1.65);
```

### Sesión 2. Teoría

Métodos:
-**void** o
El tipo de retorno. La coincidencia de tipos: entre la firma y el valor de retorno.
- package
- import
- El api de java. Jdk.

## Semana 8
### Sesión 1. (No hubo clase)
### Sesión 2. Teoría

Análisis de robustez, para usar dentro de la generación de paquetes de un proyecto

Se tienen tres distintos estereotipos:
- Entidad
- Borde
- Control

Referencia: https://academicos.azc.uam.mx/jfg/diapositivas/adsi/Unidad_7.pdf

