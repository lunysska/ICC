# Manejo de errores
## excepciones
### como manejar excepciones try, catch
### un catch puede ir acompañado de varios catch's
### un metodo puede tambien lanzar un catch com throws
### jerarquia de excepciones en Java
#### Throwable, excepcion, error
### creando nuestra propia excepcion
#### heredando de excepcion
#### creando las condiciones de creación del objeto HijaDeException
#### usando el método donde se crea el objeto

## Semana 16
### Sesión 1: Ayudantía de Teoría
#### Tema: Manejo de errores en Java
- Sintaxis de la estructura *try-catch*.
> try{
> > \<Sentencias>
> 
>}catch(\<TipoExcepcion1> \<nombreExcepcion1>){
> > \<Sentencias>
> 
>}catch(\<TipoExcepcion2> \<nombreExcepcion2>){
> > \<Sentencias>
> 
>}catch(..){
>>...
>
>}catch(\<TipoExcepcionN> \<nombreExcepcionN>){
> > \<Sentencias>
> 
>}finally{
> > \<Sentencias>
> 
>}
- **Ejemplo:** Se busca ilustrar con el siguiente código el comportamiento de *try-catch* en diferentes escenarios. Se harán diferentes modificaciones en el bloque del *try* para observar los cambios en la salida generada.
- **Versión 1:** Excepción aritmética producida directamente en el main.
```java
public class EjemploTryCatch{

    public static int divide(int a, int b){
        return a/b;
    }
    
    public static void main(String[] args){
        
        double[] arreglo = new double[]{1,2,3,4,5};
        
        try{     
 
            int c = 7/0;
           
            System.out.print("Ultima linea del bloque try.");
            
        }catch(IndexOutOfBoundsException ioobe){
            System.out.println("Excepcion de indice fuera de rango.");
            System.out.println(ioobe);
        }catch(ArithmeticException ae){
            System.out.println("Excepcion aritmetica.");
            ae.printStackTrace();
        }catch(Exception e){
            System.out.println("Se produjo una excepcion.");
            System.out.println(e);
        }finally{
            System.out.println("Bloque del finally");
        }   
    }
}
```
- **Salida**:
```
Excepcion aritmetica.
java.lang.ArithmeticException: / by zero
	at EjemploTryCatch.main(EjemploTryCatch.java:14)
Bloque del finally
```
- **Versión 2:** Excepción de índice fuera de rango.
```java
public class EjemploTryCatch{

    public static int divide(int a, int b){
        return a/b;
    }
    
    public static void main(String[] args){
        
        double[] arreglo = new double[]{1,2,3,4,5};
        
        try{     
 
            System.out.println(arreglo[5]);
           
            System.out.print("Ultima linea del bloque try.");
            
        }catch(IndexOutOfBoundsException ioobe){
            System.out.println("Excepcion de indice fuera de rango.");
            System.out.println(ioobe);
        }catch(ArithmeticException ae){
            System.out.println("Excepcion aritmetica.");
            ae.printStackTrace();
        }catch(Exception e){
            System.out.println("Se produjo una excepcion.");
            System.out.println(e);
        }finally{
            System.out.println("Bloque del finally");
        }   
    }
}
```
- **Salida**:
```
Excepcion de indice fuera de rango.
java.lang.ArrayIndexOutOfBoundsException: Index 5 out of bounds for length 5
Bloque del finally
```
- **Versión 3:** Excepción aritmética producida en el método *divide*. Se observa la pila de llamadas en la traza.
```java
public class EjemploTryCatch{

    public static int divide(int a, int b){
        return a/b;
    }
    
    public static void main(String[] args){
        
        double[] arreglo = new double[]{1,2,3,4,5};
        
        try{     
 
            int c = divide(7,0);
           
            System.out.print("Ultima linea del bloque try.");
            
        }catch(IndexOutOfBoundsException ioobe){
            System.out.println("Excepcion de indice fuera de rango.");
            System.out.println(ioobe);
        }catch(ArithmeticException ae){
            System.out.println("Excepcion aritmetica.");
            ae.printStackTrace();
        }catch(Exception e){
            System.out.println("Se produjo una excepcion.");
            System.out.println(e);
        }finally{
            System.out.println("Bloque del finally");
        }   
    }
}
```
- **Salida**:
```
Excepcion aritmetica.
java.lang.ArithmeticException: / by zero
	at EjemploTryCatch.divide(EjemploTryCatch.java:5)
	at EjemploTryCatch.main(EjemploTryCatch.java:16)
Bloque del finally
```
- **Versión 4:** Excepción de tamaño negativo de arreglo. Esta excepción es atrapada en este caso con el tipo *Exception*.
```java
public class EjemploTryCatch{

    public static int divide(int a, int b){
        return a/b;
    }
    
    public static void main(String[] args){
        
        double[] arreglo = new double[]{1,2,3,4,5};
        
        try{     
 
            String[] palabras = new String[-10];
           
            System.out.print("Ultima linea del bloque try.");
            
        }catch(IndexOutOfBoundsException ioobe){
            System.out.println("Excepcion de indice fuera de rango.");
            System.out.println(ioobe);
        }catch(ArithmeticException ae){
            System.out.println("Excepcion aritmetica.");
            ae.printStackTrace();
        }catch(Exception e){
            System.out.println("Se produjo una excepcion.");
            System.out.println(e);
        }finally{
            System.out.println("Bloque del finally");
        }   
    }
}
```
- **Salida**:
```
Se produjo una excepcion.
java.lang.NegativeArraySizeException: -10
Bloque del finally
```
- **Versión 5:** En este caso no se producen excepciones. Se observa que se ejecuta la última línea del bloque *try* (que en los casos anteriores no se ejecutaba por la excepción producida).
```java
public class EjemploTryCatch{

    public static int divide(int a, int b){
        return a/b;
    }
    
    public static void main(String[] args){
        
        double[] arreglo = new double[]{1,2,3,4,5};
        
        try{     
 
            System.out.print("Ultima linea del bloque try.");
            
        }catch(IndexOutOfBoundsException ioobe){
            System.out.println("Excepcion de indice fuera de rango.");
            System.out.println(ioobe);
        }catch(ArithmeticException ae){
            System.out.println("Excepcion aritmetica.");
            ae.printStackTrace();
        }catch(Exception e){
            System.out.println("Se produjo una excepcion.");
            System.out.println(e);
        }finally{
            System.out.println("Bloque del finally");
        }   
    }
}
```
- **Salida**:
```
Ultima linea del bloque try.Bloque del finally
```

## Semana 16
### Sesión 2: Ayudantía de Teoría
#### Tema: Manejo de errores en Java
- **Ejemplo: try-catch en un ciclo**
- En este ejemplo se implementa un programa que solicita al usuario dos enteros para calcular su división entera. Se usa un bloque *try-catch* para atrapar el posible error de división entre cero, dentro de un ciclo para volver a solicitar los enteros en caso de que se requiera. Si el usuario ingresa el cero como divisor cinco veces seguidas el programa termina mostrando un mensaje de intentos máximos.
```java
import java.util.Scanner;

public class EjemploTryCatch2{
    
    public static void main(String[] args){

        int contador = 0;        
        int a;
        int b;
        int c;
        boolean bandera = false;
        
        Scanner in = new Scanner (System.in);
        
        do{
            contador++;
        
            System.out.print("Ingresa numerador y denominador: ");
            a = in.nextInt();
            b = in.nextInt();
        
            try{
                c = a/b;
                bandera = true;
                System.out.println("El cociente entero es: "+c);
            }catch(ArithmeticException ae){
                System.out.println("Error aritmetico. Favor de reintentar.");
            }
        
        }while(contador<5 && bandera == false);
        
        if(contador == 5 && bandera == false)
            System.out.println("Numero de intentos maximo alcanzado.");

    }

}
```
- En el ejemplo anterior solo se está atrapando la excepción ArithmeticException. Todavía podrían producirse otras excepciones no atrapadas, como una InputMismatchException en la lectura.
- **Ejemplo: Creación de una excepción propia**
- **Motivación:** Observe el siguiente código:
```java
public class EjemploTryCatch3{
    
    public static void main(String[] args){

        double a = 5.0;
        double b = 0.0;
        double c;
        
        try{
            c = a/b;
            System.out.println("El valor de c es: "+c);
        }catch(Exception e){
            System.out.println(e);
        }   
    }
}
```
- Aunque pueda parecer contraintuitivo, la compilación y ejecución del código anterior no produce excepción alguna. Se imprimiría en consola el valor "Infinity", que Java considera en *double* (al igual que -Infinity). El ejemplo siguiente implementa una clase para tener una nueva excepción, que se usa después en un método para dividir *doubles* que no permita dividir entre cero.
```java
class DivisionPorCeroDoubleException extends Exception{
    public DivisionPorCeroDoubleException(String mensaje){
        super(mensaje);
    }
}

public class EjemploTryCatch4{

    public static double divide(double a, double b) throws DivisionPorCeroDoubleException{
        if(b==0.0) // Esto no es buena practica, es conveniente usar intervalos
            throw new DivisionPorCeroDoubleException("El divisor no puede ser cero.");
        return a/b;
    }
    
    public static void main(String[] args){

        double a = -5.0;
        double b = 0.0;
        double c;
        
        try{
            c = divide(a,b);
            System.out.println("El valor de c es: "+c);
        }catch(DivisionPorCeroDoubleException dpcde){
            System.out.println(dpcde);
            c = a/b;
        }
        
        System.out.println("El valor de c es: "+c);
        
    }

}
```
- En este caso, como para poder imprimir el valor de *c* después del bloque *try-catch* *c* debe tener algún valor, se opta por realizar la divisón habitual después de haber atrapado la excepción.
