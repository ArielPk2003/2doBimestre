# Programación I 2do Bimestre
* @autor: Harryson Montesdeoca
* @fecha: 10-03-2023
* @descripción: Una breve pero útil recopilación de información de los temas vistos a lo largo del 2do bimestre. 
 
# Punteros en C++
* Los punteros son variables que almacenan direcciones de memoria en lugar de valores. Son una característica poderosa y esencial en C++, y pueden usarse para lograr una variedad de cosas útiles, como el manejo de memoria dinámica y la implementación de estructuras de datos avanzadas.

## Declaración de punteros
* Un puntero se declara usando el operador * después del tipo de dato. Por ejemplo, para declarar un puntero a un entero, se usa la siguiente sintaxis:

``` C++
int* mi_puntero;
```
## Asignación de valores a punteros
* Los punteros se asignan valores usando el operador & para obtener la dirección de una variable existente. Por ejemplo, para asignar la dirección de una variable x a un puntero mi_puntero, se usa la siguiente sintaxis:

``` C++

int x = 10;
int* mi_puntero = &x;
```

## Acceso al valor almacenado en una dirección de memoria
* Para acceder al valor almacenado en la dirección de memoria apuntada por un puntero, se usa el operador *. Por ejemplo, para imprimir el valor de x usando el puntero mi_puntero, se usa la siguiente sintaxis:

``` C++

cout << *mi_puntero << endl;
```
## Punteros nulos
* Un puntero nulo es un puntero que no apunta a ninguna dirección de memoria válida. Se declara como sigue:

``` C++

int* mi_puntero_nulo = nullptr;
``` 

## Operaciones aritméticas de punteros
* Los punteros pueden ser usados en operaciones aritméticas para acceder a otras posiciones de memoria. Por ejemplo, para acceder al segundo elemento de un arreglo mi_arreglo de enteros, se puede hacer lo siguiente:

``` C++

int* segundo_elemento = mi_arreglo + 1;
``` 

## Punteros en arrays
* Para acceder a los elementos de un array mediante un puntero, se puede utilizar la notación de subíndice o la aritmética de punteros.

* Notación de subíndice
La notación de subíndice es la forma más común de acceder a los elementos de un array en C++. La sintaxis es la siguiente:

``` C++
int hola_profe[5] = {1, 2, 3, 4, 5};
int* ptr = hola_profe; // Se asigna la dirección de memoria del primer elemento del array al puntero

cout << hola_profe[0] << endl; // Imprime el primer elemento del array
cout << ptr[0] << endl; // Imprime el primer elemento del array utilizando el puntero
```
# Punteros en matrices
* Para acceder a los elementos de una matriz mediante un puntero, se debe tener en cuenta la estructura de la matriz y la forma en que se almacenan los elementos en la memoria.

## Matrices de una dimensión
* En una matriz de una dimensión, los elementos se almacenan en una ubicación contigua en la memoria, igual que en un array. Para acceder a los elementos de una matriz de una dimensión mediante un puntero, se puede utilizar la misma sintaxis que para acceder a los elementos de un array.

``` C++
int mi_matriz[5] = {1, 2, 3, 4, 5};
int* ptr = mi_matriz; // Se asigna la dirección de memoria del primer elemento de la matriz al puntero

cout << mi_matriz[0] << endl; // Imprime el primer elemento de la matriz
cout << ptr[0] << endl; // Imprime el primer elemento de la matriz utilizando el puntero
``` 
# Archivos

la manipulación de archivos es posible gracias a la librería fstream, que proporciona clases y funciones para trabajar con archivos de texto y binarios.

Para utilizar la librería fstream, se debe incluir la cabecera correspondiente al inicio del archivo:

``` C++
#include <fstream>
```
* Para abrir un archivo, se utiliza la clase fstream y se llama al método open() con el nombre del archivo y el modo de apertura como parámetros. Los modos de apertura más comunes son ios::in para abrir un archivo para lectura, ios::out para abrir un archivo para escritura y ios::app para abrir un archivo y añadir datos al final.

``` C++
#include <fstream>
using namespace std;

int main() {
    // Abrir un archivo para escritura
    ofstream outfile;
    outfile.open("ejemplo.txt");

    // Escribir en el archivo
    outfile << "Hola, mundo!" << endl;

    // Cerrar el archivo
    outfile.close();

    // Abrir un archivo para lectura
    ifstream infile;
    infile.open("ejemplo.txt");

    // Leer del archivo
    string line;
    getline(infile, line);

    // Imprimir la línea leída
    cout << line << endl;

    // Cerrar el archivo
    infile.close();

    return 0;
}
```
# Estructuras 
* Una estructura es un tipo de dato compuesto que permite agrupar diferentes variables bajo un solo nombre. Cada variable en una estructura se llama miembro o campo, y se puede acceder a ellos utilizando el operador de punto . o el operador de flecha ->.

* Para definir una estructura, se utiliza la palabra clave struct, seguida del nombre de la estructura y los miembros entre llaves:

``` C++
struct Persona {
    string nombre;
    int edad;
    float altura;
};
```
En este ejemplo, se define una estructura llamada Persona con tres miembros: nombre, edad y altura. Cada miembro tiene un tipo de dato diferente, y se puede acceder a ellos utilizando el operador de punto .:

``` C++
Persona p;
p.nombre = "Juan";
p.edad = 25;
p.altura = 1.75;
```
* En este caso, se crea una instancia de la estructura Persona llamada p y se asignan valores a sus miembros utilizando el operador de punto ..

* También es posible crear un puntero a una estructura utilizando el operador de dirección &:

``` C++
Persona* ptr = &p;
```
En este ejemplo, se crea un puntero ptr que apunta a la estructura p utilizando el operador de dirección &. Para acceder a los miembros de la estructura a través del puntero, se utiliza el operador de flecha ->:

``` C++
cout << "Nombre: " << ptr->nombre << endl;
cout << "Edad: " << ptr->edad << endl;
cout << "Altura: " << ptr->altura << endl;
```

* En este caso, se imprime en la consola los valores de los miembros de la estructura p a través del puntero ptr.

* En resumen, las estructuras en C++ permiten agrupar diferentes variables bajo un solo nombre y acceder a ellas utilizando el operador de punto . o el operador de flecha ->. También es posible crear punteros a estructuras utilizando el operador de dirección & y acceder a los miembros a través del operador de flecha ->.

# Pilas
* Las Pilas son estructuras de datos lineales que funcionan siguiendo el principio LIFO (Last In, First Out), lo que significa que el último elemento en ser ingresado es el primero en ser retirado. En C++, las Pilas pueden ser implementadas usando arreglos o listas enlazadas.

## Operaciones Básicas en Pilas
Las operaciones básicas en Pilas son:
``` C++
push(): Inserta un elemento en la parte superior de la Pila.
pop(): Elimina el elemento superior de la Pila.
top(): Retorna el elemento superior de la Pila.
empty(): Verifica si la Pila está vacía.
```

# Autómatas Finitos Deterministas
* Los autómatas finitos deterministas (AFD) son una herramienta utilizada en teoría de la computación para modelar sistemas que siguen un conjunto de reglas específicas. Los AFD se pueden representar mediante un conjunto finito de estados, un alfabeto finito y una función de transición que describe cómo se mueve el autómata de un estado a otro al leer un símbolo del alfabeto.

# Operación de un AFD
El funcionamiento de un AFD se puede dividir en dos etapas: la etapa de lectura y la etapa de aceptación. Durante la etapa de lectura, el autómata lee los símbolos de entrada y cambia de estado siguiendo la función de transición. Durante la etapa de aceptación, el autómata determina si la cadena de entrada debe ser aceptada o rechazada. La cadena de entrada se acepta si el autómata llega a un estado de aceptación al final de la etapa de lectura.

* Gracias por los conocimientos de este semestre :D