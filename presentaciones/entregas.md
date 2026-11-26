
# Entrega 6.

Se sube en el git en:
**teoria/tarea6ConstructoresMenu**

#### Ejercicio: Constructores de la clase `Cuenta`

Implementa una clase `Cuenta` con los siguientes atributos:

- `titular`: `String`
- `saldo`: `double`
- `fechaCreacion`: `int`
- `tipo: char`

Define cuatro constructores que permitan:

1. Crear una cuenta sin proporcionar datos iniciales.
2. Crear una cuenta indicando únicamente el titular
3. Crear una cuenta proporcionando todos sus atributos 
4. Crear una cuenta indicando el titular y el número de cuenta, estableciendo automáticamente un saldo inicial de `100.0`.

Crea objetos utilizando cada uno de los cuatro constructores, desde el Main, para pruebas


#### Ejercicio: Menú del sistema bancario

Implementa una clase `Menu` que permita interactuar con la clase `Cuenta` mediante un menú de consola.

El menú deberá ofrecer las siguientes opciones:

1. **Crear cuenta:** solicitar los datos necesarios y crear un objeto `Cuenta` utilizando alguno de los constructores disponibles.
2. **Consultar cuenta:** mostrar el titular, saldo y número de cuenta.
3. **Depositar dinero:** solicitar una cantidad y realizar un depósito en la cuenta.
4. **Retirar dinero:** solicitar una cantidad y realizar un retiro de la cuenta.
5. **Salir:** finalizar la ejecución del programa.

Organiza el programa en tres clases:

- `Cuenta`: contiene los atributos, constructores y métodos para depositar y retirar dinero.
- `Menu`: muestra las opciones y captura la selección del usuario.
- `Main`: contiene el método `main` e inicia la ejecución del programa.

**Nota:** El menú deberá permanecer activo hasta que el usuario seleccione la opción 5.
