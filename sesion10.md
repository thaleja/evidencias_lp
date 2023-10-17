<!-- No borrar o modificar -->
[Inicio](./index.md)

## Sesión 10 


<!-- Su documentación aquí -->

# Actividad: Prueba, ejecución y explicación de ejercicios de lógica de programación.

Selecciona dos ejercicios de la sesión 10, impleméntalos, ejecútalos y proporciona una explicación detallada de cada uno

# DESARROLLO

1. 

``` java
package com.mycompany.formacionsubgrupos;
import java.util.ArrayList;
import java.util.Collections;
import java.util.Scanner;
/**
 *
 * @author Alejandra Tamayo Hernandez 
 */
public class FormacionSubgrupos {

   public static void main(String[] args) {
      Scanner input = new Scanner(System.in);
      ArrayList<String> integrantes = new ArrayList<String>();

      // Solicitar lista de integrantes
      System.out.print("Ingrese la lista de integrantes separados por coma: ");
      String inputIntegrantes = input.nextLine();
      String[] integrantesArray = inputIntegrantes.split(",");
      for (String integrante : integrantesArray) {
         integrantes.add(integrante.trim());
      }

      // Solicitar cantidad de subgrupos
      System.out.print("Ingrese la cantidad de subgrupos que desea formar: ");
      int cantidadSubgrupos = input.nextInt();

      // Formar subgrupos
      int integrantesPorSubgrupo = integrantes.size() / cantidadSubgrupos;
      int integrantesSobrantes = integrantes.size() % cantidadSubgrupos;
      Collections.shuffle(integrantes); // mezclar la lista de integrantes para formar subgrupos aleatorios
      int indiceInicial = 0;
      for (int i = 0; i < cantidadSubgrupos; i++) {
         int integrantesEnSubgrupo = integrantesPorSubgrupo;
         if (integrantesSobrantes > 0) {
            integrantesEnSubgrupo++;
            integrantesSobrantes--;
         }
         int indiceFinal = indiceInicial + integrantesEnSubgrupo;
         ArrayList<String> subgrupo = new ArrayList<String>(integrantes.subList(indiceInicial, indiceFinal));
         indiceInicial = indiceFinal;
         System.out.printf("Subgrupo %d: %s%n", i + 1, subgrupo);
      }
   }
}
    
```
### Explicación: 

El código anterior es una implementación en Java de un algoritmo para formar subgrupos a partir de una lista de integrantes.

El programa comienza importando las clases y paquetes necesarios:

``` java
package com.mycompany.formacionsubgrupos;
import java.util.ArrayList;
import java.util.Collections;
import java.util.Scanner;

```
Después, se define la clase principal `FormacionSubgruposque` contiene el método `main`:

``` java
public class FormacionSubgrupos {
    public static void main(String[] args) {

```
Se crea una instancia de la clase `Scanner` para poder leer la entrada del usuario:

``` java
Scanner input = new Scanner(System.in);
```
Se declara una lista `integrantes` para almacenar los nombres de los integrantes:

``` java
ArrayList<String> integrantes = new ArrayList<String>();

```

Se le solicita al usuario ingresar la lista de integrantes separados por coma:

``` java
System.out.print("Ingrese la lista de integrantes separados por coma: ");
String inputIntegrantes = input.nextLine();
```
La entrada ingresada se divide en un array de cadenas utilizando la función `split(",")` para obtener los nombres individuales de los integrantes:

``` java
String[] integrantesArray = inputIntegrantes.split(",");

```
Luego, se recorre el array de integrantes y se agrega cada integrante a la lista `integrantes`:

``` java 
for (String integrante : integrantesArray) {
    integrantes.add(integrante.trim());
}

```
A continuación, se solicita al usuario ingresar la cantidad de subgrupos que desea formar:

``` java 
System.out.print("Ingrese la cantidad de subgrupos que desea formar: ");
int cantidadSubgrupos = input.nextInt();

```
Se calcula la cantidad de integrantes que habrá en cada subgrupo y la cantidad de integrantes que sobran:

``` java
int integrantesPorSubgrupo = integrantes.size() / cantidadSubgrupos;
int integrantesSobrantes = integrantes.size() % cantidadSubgrupos;

```
Se mezcla la lista de integrantes utilizando la función `shuffle()` de la clase `Collections`
para formar subgrupos aleatorios:

``` java
Collections.shuffle(integrantes); 

```
Se establece un índice inicial para recorrer la lista de integrantes y formar los subgrupos de acuerdo a la cantidad de integrantes por subgrupo:

``` java
int indiceInicial = 0;

```
Se utiliza un bucle `for` para formar los subgrupos:

``` java
for (int i = 0; i < cantidadSubgrupos; i++) {
    int integrantesEnSubgrupo = integrantesPorSubgrupo;
    if (integrantesSobrantes > 0) {
        integrantesEnSubgrupo++;
        integrantesSobrantes--;
    }
    int indiceFinal = indiceInicial + integrantesEnSubgrupo;
    ArrayList<String> subgrupo = new ArrayList<String>(integrantes.subList(indiceInicial, indiceFinal));
    indiceInicial = indiceFinal;
    System.out.printf("Subgrupo %d: %s%n", i + 1, subgrupo);
}

```
Dentro del bucle, se calcula la cantidad de integrantes que habrá en el subgrupo actual, teniendo en cuenta si hay integrantes sobrantes que deben ser distribuidos entre los subgrupos. Luego, se establece un índice final para obtener el rango de integrantes que corresponde al subgrupo actual. Se crea un nuevo `ArrayList` llamado `subgrupo` utilizando el método `subList()` de la lista `integrantes` para obtener los integrantes del rango establecido. Finalmente, se actualiza el índice inicial para el siguiente subgrupo y se imprime en pantalla el número de subgrupo y sus integrantes.

Una vez que el bucle ha terminado, el programa finaliza su ejecución.

2. 

``` java
import java.util.Scanner;

public class IMC {
   public static void main(String[] args) {
      Scanner input = new Scanner(System.in);
      double weight, height, imc;
      
      // Solicita el peso y la altura
      System.out.print("Ingrese su peso en kilogramos: ");
      weight = input.nextDouble();
      System.out.print("Ingrese su altura en metros: ");
      height = input.nextDouble();

      // Calcula el IMC
      imc = weight / (height * height);

      // Muestra el resultado en la consola
      System.out.printf("Su IMC es %.2f", imc);
   }
}
```

### Explicación

Es un programa que calcula el Índice de Masa Corporal (IMC) a partir del peso y la altura ingresados ​​por el usuario.

Se importa la clase `Scanner` para poder leer la entrada del usuario:

``` java
import java.util.Scanner;

```
Definimos la clase `IMC` que contiene el método `main`:

``` java
public class IMC {
   public static void main(String[] args) {

```
Creamos una instancia de la clase `Scanner` para leer la entrada del usuario:

``` java
Scanner input = new Scanner(System.in);

```
Declaramos las variables `weight`, `height` y `imc` para almacenar el peso, la altura y el IMC calculado, respectivamente:

``` java
double weight, height, imc;

```
Solicitamos al usuario ingresar su peso en kilogramos:

``` java
System.out.print("Ingrese su peso en kilogramos: ");
weight = input.nextDouble();

```
Solicitamos al usuario ingresar su altura en metros:

``` java
System.out.print("Ingrese su altura en metros: ");
height = input.nextDouble();

```
Calculamos el IMC dividiendo el peso entre el cuadrado de la altura:

``` java
imc = weight / (height * height);

```
Mostramos el resultado en la consola utilizando el método `printf()` para formatear la salida y mostrar el resultado con dos decimales:

``` java
System.out.printf("Su IMC es %.2f", imc);

```
Una vez que se muestra el resultado, el programa finaliza su ejecución.