# Módulo 3.Análisis y Diseño Orientado a Objetos

## Semana 3
### Sesión 2 
#### Teoria

##### El paradigma de programación orientado a objetos

La definición de:
Clases
Objetos. Instancias de clases
Mensajes. Paso de mensajes

Sus características principales:
Abstracción
Encapsulación
Herencia
Polimorfismo

#### Ejercicios teoria

Ver un ejemplo (tal vez el de las derivadas de polinomios de grado k), y bosquejarlo con este paradigma, definiendo clases, empezar el algoritmo creando objetos de las clases definidas y mandar a llamar métodos y mensajes

## Semana 4
### Sesión 1 (ayudantía de teoría)
#### Ejercicio: Derivada de un polinomio de grado k
Bosquejar el algoritmo para calcular la derivada de un polinomio de grado k empleando Programación Orientada a Objetos.
- Definición de polinomio.
- Derivada de un polinomio (fórmula y ejemplos).
- Tipos de métodos: constructores, de acceso, de actualización o modificación, de implementación y auxiliares.  

Se consideraron dos alternativas:
1. Emplear una clase Monomio y otra clase Polinomio, que tuviera entre sus atributos un arreglo de Monomios.
2. Emplear directamente una clase Polinomio únicamente.  

Se optó por la segunda opción.  
Atributos de la clase Polinomio:  
    -- grado  
    -- coeficientes[]  
Métodos de la clase Polinomio:  
    \+ Polinomio()  
    \+ Polinomio(grado, coeficientes)  
    \+ imprime()  
    \+ deriva()  
    \+ get_grado()  
    \+ get_coeficientes()  
    \+ set_grado(grado)  
    \+ set_coeficientes(coeficientes)  
    \+ suma()  
    \+ multiplica()  
    \+ evalua(x)  
Se comenzó a trabajar el pseudocódigo del método deriva(), pero quedó inconcluso.

### Sesión 1: Teoría
#### Tema:  Las características del PPOO

* atributos: caracteristicas de las clases
* métodos: acciones que los objetos de una clase realizan.

- abstracción
- encapsulacion
- herencia
- polimorfismo
