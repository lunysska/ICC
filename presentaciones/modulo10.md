## Semana 15

### Sesión 2: Ayudantía de Teoría
#### Tema: Tipos genéricos
- Se aplicó el [miniExamen7.pdf](../miniExamenes/miniExamen7.pdf)
- Muchas veces el comportamiento de un algoritmo o estructura de datos (como pudiera ser algún tipo de colección) no depende del tipo de los elementos que recibe. En Java, que tiene una jerarquía de clases con raíz única (la clase Object) esto puede implementarse usando Object como el tipo. Sin embargo, esto tiene al menos dos grandes desventajas:
- - 1. Esto fuerza al programador a usar castings al obtener elementos del algoritmo/estructura.
- - 2. Esto permite crear estructuras con elementos heterogéneos (es decir, de diferentes tipos, lo que puede ser considerado una mala práctica).
- **Ejemplo:** Considérese la siguiente clase Par, que representa un par de ordenado de objetos de cualquier tipo (adicionalmente se incluye una clase Rectangulo).
```java
class Rectangulo{

    private double largo;
    private double ancho;
    
    public Rectangulo(double largo, double ancho){
        this.largo = largo;
        this.ancho = ancho;
    }

}

public class Par{

    private Object primero;
    private Object segundo;
    
    public Par(Object primero, Object segundo){
        this.primero = primero;
        this.segundo = segundo;
    }
    
    public Object getPrimero(){
        return primero;
    }
    
    public Object getSegundo(){
        return segundo;
    }
    
    public static void main(String[] args){
        
        Par dosCadenas = new Par("Cadena 1","Cadena 2");
        
        // String c1 = dosCadenas.getPrimero();
        // Se produciria el error: incompatible types: Object cannot be converted to String
        // Debe usarse un casting forzosamente
        
        String c1 = (String)dosCadenas.getPrimero();
        
        System.out.println(c1);
        
        Rectangulo r1 = new Rectangulo(1.0,2.0);
        
        Par dosCosas = new Par("Cadena",r1);
        // Este par contiene objetos de dos tipos distintos
        
    }

}
```
- Estos dos problemas son los que resuelven principalmente los *tipos genéricos* (o simplemente *genéricos*) en Java. En Java, una clase se define *genérica* especificando un *parámetro genérico* entre los símbolos "<" y ">". La convención para el *parámetro genérico* es usar una única letra mayúscula, generalmete una letra T (de *Type*). A continuación se muestra el código anterior implementado con *genéricos*.
```java
class Rectangulo{

    private double largo;
    private double ancho;
    
    public Rectangulo(double largo, double ancho){
        this.largo = largo;
        this.ancho = ancho;
    }

}

public class Par<T>{

    private T primero;
    private T segundo;
    
    public Par(T primero, T segundo){
        this.primero = primero;
        this.segundo = segundo;
    }
    
    public T getPrimero(){
        return primero;
    }
    
    public T getSegundo(){
        return segundo;
    }
    
    public static void main(String[] args){
        
        Par<String> dosCadenas = new Par<String>("Cadena 1","Cadena 2");
        
        String c1 = dosCadenas.getPrimero();
        // Ya no es necesario el casting
        
        System.out.println(c1);
        
        Rectangulo r1 = new Rectangulo(1.0,2.0);
        
        Par<Object> dosCosas = new Par<Object>("Cadena",r1);
        // Todavia es posible crear un Par de objetos de distintos tipos,
        // pero ahora se debe especificar explicitamente el tipo Object
        
    }

}
```
- Se dice entonces que la clase Par es *genérica*, o que Par es un *tipo genérico*, siendo *T* su *parámetro genérico*. Cada instancia de la clase Par debe especificar el tipo que empleará, el cual puede ser cualquier tipo no primitivo.
- Las colecciones en Java (que son implementadas, por ejemplo, en las clases ArrayList, LinkedList o Hashmap), utilizan *tipos genéricos*. A continuación se muestra un ejemplo de uso.
```java
	ArrayList<String> lista = new ArrayList<>(); // Del lado derecho es opcional especificar el tipo
	lista.add("Cadena 1");
	String texto = lista.get(0); // No se necesita usar un casting
```
