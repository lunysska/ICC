# Herencia y diseño de clases

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
