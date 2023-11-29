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
