# 8. Herencia y diseño de clases

## Qué es herencia en el PPOO
## Qué ventajas tiene la herencia.
## Cómo es la herencia en java. Su uso y sintáxis
## Ejemplo: La clase madre: Empleado y sus clases hijas: Secretaria, Director, etc.
## Polimorfismo
## Sobreescritura de metodos
## La palabra super.
## Clase madre. Object
## Polimorfismo
## Ventajas del polimorfismo

## Semana 13

### Sesión 2: Ayudantía de Teoría
#### Tema: Herencia
- La herencia permite reutilizar de forma inteligente código ya hecho, a través de la extensión de clases ya implementadas. En una relación de herencia, se le llama clase hija o subclase a la que hereda de otra clase definida previamente (llamada clase padre o madre o superclase), los atributos y métodos definidos como públicos y protegidos. Después puede extenderse la clase hija a través de la definición de nuevos atributos y métodos, así como la sobreescritura de estos.
- La herencia permite construir jerarquías de clases y evitar tener que "volver a reinventar la rueda".
- **Ejemplo:** (Adaptado del sitio web de Ricardo Moya: https://jarroba.com/herencia-en-la-programacion-orientada-a-objetos-ejemplo-en-java/ )
- Se busca representar a los diferentes integrantes de un equipo de fútbol. Inicialmente se consideran tres clases: Futbolista, Entrenador y Terapeuta. Se muestra a continuación un diseño inicial sin herencia (por brevedad, se omiten los constructores, setters y getters).

| Futbolista | Entrenador | Terapeuta |
|------------| --------------|--------|
| \- id: int | \- id: int | \- id: int |
| \- nombre: String| \- nombre: String| \- nombre: String |
| \- apellido: String| \- apellido: String| \- apellido: String|
| \- edad: int| \- edad: int| \- edad: int|
|\- dorsal: int| \- idFederacion: String | \- especialidad: String |
| \- posicion: String | | \- experiencia: int |
| \+ concentrarse( ): void| \+ concentrarse( ): void| \+ concentrarse( ): void|
| \+ viajar( ): void| \+ viajar( ): void| \+ viajar( ): void|
| \+ jugarPartido( ): void| \+dirigirPartido( ): void | \+ asistirJugador( ): void |
| \+ entrenar( ): void | \+dirigirEntrenamiento( ): void | |

- Con este diseño se tendrían tres archivos como:
```java
public class Futbolista{
	private int id;
	private String nombre;
	.
	.
	.
	public void concentrarse(){
		.
		.
		.
	}
	public void viajar(){
		.
		.
		.
	}	
	.
	.
	.
}
```
- Y de manera similar para las clases Entrenador y Terapeuta.
- Se observa que cuatro de los atributos y dos de los métodos son comunes a las tres clases. Se propone entonces un diseño que haga uso de la herencia, con una clase padre IntegranteEquipo. El nuevo diseño se muestra a continuación (las clases Futbolista, Entrenador y Terapeuta heredan de IntegranteEquipo, por lo que solo se enlistan sus atributos y métodos adicionales).

|IntegranteEquipo| Futbolista | Entrenador | Terapeuta |
|----------------|------------| --------------|--------|
|\# id: int| \- dorsal: int | \- idFederacion: String | \- especialidad: String  |
|\# nombre: String| \- posicion: String | \+dirigirPartido( ): void| \- experiencia: int  |
|\# apellido: String| \+ jugarPartido( ): void | \+dirigirEntrenamiento( ): void| \+ asistirJugador( ): void|
|\# edad: int| \+ entrenar( ): void | | |
|\+ concentrarse( ): void||  | |
|\+ viajar( ): void|  | | |

- Con este diseño se tendrían cuatro archivos como:
```java
public class IntegranteEquipo{
	protected int id;
	protected String nombre;
	.
	.
	.
	public void concentrarse(){
		.
		.
		.
	}
	public void viajar(){
		.
		.
		.
	}	
}
```

```java
public class Futbolista extends IntegranteEquipo{
	private int dorsal;
	private String posicion;
	public void jugarPartido(){
		.
		.
		.
	}
	public void entrenar(){
		.
		.
		.
	}	
}
```
- Y de modo similar para las clases Entrenador y Terapeuta.

## Semana 14

### Sesión 1: Ayudantía de Teoría
#### Tema: Modificadores de acceso en Java
- Se aplicó el [miniExamen6.pdf](../miniExamenes/miniExamen6.pdf)
- En Java se cuenta con cuatro modificadores de acceso. Los niveles de visibilidad que proporcionan se resumen en la siguiente tabla.

| Visibilidad | public | protected | default / package | private |
|-------------|--------|-----------|-------------------|---------|
|Desde la misma clase|Sí|Sí|Sí|Sí|
|Desde el mismo paquete|Sí|Sí|Sí|No|
|Desde una subclase del mismo paquete|Sí|Sí|Sí|No|
|Desde una subclase en otro paquete|Sí|Sí|No|No|
|Desde cualquier clase|Sí|No|No|No|
- **Ejemplo:** El siguiente ejemplo tiene la finalidad de ilustrar el funcionamiento de los modificadores de acceso, mostrando diferentes casos que se pueden presentar. El código tiene solo fines ilustrativos, no es una aplicación realista ni se apega a las buenas prácticas (precisamente para poder ejemplificar comportamientos indeseados).
- Considérese la siguiente estructura de archivos:
> src/
> > paquete1/
> > > Vehiculo.java
> > > Auto.java
> >
> > paquete2/
> > > PruebasVehiculo.java
- La clase Auto heredará de la clase Vehiculo, mientras que la clase PruebasVehiculo importará a la clase Vehiculo (pero no heredará). Se muestran a continuación los códigos.
- **Vehiculo.java**
```java

package paquete1;
 
public class Vehiculo{

    protected int id;
    public int precio;
    private int velocidad;

    public Vehiculo(int id, int precio, int velocidad){
        this.id = id;
        this.precio = precio;
        this.velocidad = velocidad;
    }

    public int getId(){
        return id;
    }
    
    private int getPrecio(){
        return precio;
    }

    protected int getVelocidad(){
        return velocidad;
    }
        
    public void setVelocidad(int velocidad){
        this.velocidad = velocidad;
    }
    
    public void imprime(){
        System.out.println("id: "+id);
        System.out.println("precio: "+precio);
        System.out.println("velocidad: "+velocidad);
    }
    
}
```

- **Auto.java**
```java
package paquete1;

class Auto extends Vehiculo{

    private String placa;
    
    public Auto(int id, int precio, int velocidad, String placa){
        super(precio,velocidad,id);
        this.placa = placa;
    }
    
    public void imprime(){
        super.imprime();
        System.out.println("placa: "+placa);
    }
    
    public static void main(String[] args){
        
        Auto a1 = new Auto(37,50000,200,"A00AAA");
        a1.imprime();
        
        a1.precio = 100; // Funciona sin problemas
       
        // a1.velocidad = 200;
        // Error en compilacion: velocidad has private access
        
        a1.id = 1; // Funciona sin problemas

        a1.imprime();
        
        a1.setVelocidad(250); // Funciona sin problemas
        a1.imprime();
        
        System.out.println(a1.getId()); // Funciona sin problemas
        
        // System.out.println(a1.getPrecio());
        // Error en compilacion: cannot find symbol
         
        System.out.println(a1.getVelocidad()); // Funciona sin problemas
    }
}
```

- **PruebasVehiculo.java**
```java
package paquete2;
import paquete1.Vehiculo;
 
class PruebasVehiculo{

    public static void main(String[] args){
        
        Vehiculo v1 = new Vehiculo(40,400000,180);
        v1.imprime();
        
        v1.precio = 100; // Funciona sin problemas
        
        // v1.velocidad = 200;
        // Error en compilacion: velocidad has private access
        
        // v1.id = 1;
        // Error en comp: id has protected access in Vehiculo
        
        v1.imprime();
        
        v1.setVelocidad(250); // Funciona sin problemas
        v1.imprime();

        System.out.println(v1.getId()); // Funciona sin problemas
        
        // System.out.println(v1.getPrecio());
        // Error en compilacion: getPrecio() has private access in Vehiculo
        
        // System.out.println(v1.getVelocidad());
        // Error en compilacion: getVelocidad() has protected access in Vehiculo
    }

}
```
## Sesion k. Teoria
### Resumen de Herencia

### Clase madre que pierde el constructor por omisión

#### Sobrecarga del constructor de la madre, usando this()

### Clase hija que pierde el constructor por omisión
#### usando super() como primer línea del constructor

### Revisión de cómo se ejecuta en la memoria cuando se crea un objeto de la clase Hija con constructor
#### Object como "tope" en el proceso de ejecución de inicialización.

### Clases Wrapper en Java

### Clases abstractas e Interfaces
#

