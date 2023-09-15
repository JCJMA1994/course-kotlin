Variables
==========
Existen dos tipos de variables en Kotlin
var y val

* var -> este valor puede cambiar a lo largo de la ejecucion
  del codigo. Es la abreviatura de "variable"


* val -> representa un valor unico, este valor no
  se puede cambiar a lo largo de la ejecucion.
  Esla abreviatura de "valor".

 ``` kotlin
fun main() {
    // ERROR! val cannot be reassigned
    val value = "A"
    value = "B" 

    // OK! var can be assigned
    var variable = "A"
    variable = "B"
}
```
Tipos
======
Cada variable tiene un tipo especifico de forma
prederteminado por el valor inicial.

Ejemplo:

La variable **str** tiene un valor inicial de asignado
tipo String
 ``` kotlin
fun main() {
    var str = "ABC" // The type of str is String
    str = "XYZ"
    str = 42 // ERROR! Int value cannot be assigned to a variable of type String
    str = true // ERROR! Boolean value cannot be assigned to a variable of type String
}
```
Para espeficiar un tipo se utiliza dos puntos y el nombre del tipo
 ``` kotlin
fun main() {
    var str: String = "ABC"
    str = "XYZ"
}
```
Para especificar varios tipos en se usa **Any**
 ``` kotlin
fun main() {
    var x: Any = "ABC"
    println(x) // ABD
    x = 123
    println(x) // 123
    x = true
    println(x) // true
} 
```
---
Condiciones
==========
***if, if-else***

En la condicion **if** verifica si la condicion es verdadera
 ``` kotlin
fun main() {
    val num = 10
    if( num <= 20){
        print("$num es menor a 20")
    }
} 
```

En la condicion **if-else**, se verifica la condicion y si no cumple se devuelve la parte
del else

``` kotlin
fun main() {
    val num = 30
    if(num <= 20){
        print("$num es menor a 20")
    }else{
        print("$num es mayor a 20")
    }
} 
```
La condicion if se puede usar como variable.
``` kotlin
fun main() {
    val num = 10
    val error = if( num <= 20) "$num es menor a 20" else $num es mayor a 20"
    print(error)
} 
```
---
***when***

La instrucción ***when*** es una alternativa a if-else-if. En cada rama de la instrucción when, puede especificar un predicado
y un cuerpo. El cuerpo se ejecutará solo para el primer predicado que devuelva true
``` kotlin
fun main() {
println("Is it going to rain?")
val probability = 70
        when {
            probability < 40 -> {
                 println("Unlikely")
            }
            probability <= 80 -> {
                println("Likely")
            }
            probability < 100 -> {
                 println("Yes")
            }
            else -> {
                println("What?")
            }
        }
}
```
Cuando solo se dispone de una instruccion se pueden omitir las llaves.

When tambien se puede usar como expresion, la unica condicion es que tiene que tener
un bloque ***else***

``` kotlin
fun main() {
println("Is it going to rain?")
val probability = 70
val text = when {
            probability < 40 -> "Unlikely"
            probability <= 80 -> "Likely"
            probability < 100 -> "Yes"
            else -> "What?"
          }
          print(text)
}
```

También hay otra forma de la instrucción when. Si agrega un valor entre paréntesis después de la
palabra clave when, entonces en cada rama, Kotlin compara este valor con otros valores.

***when con un valor***
``` kotlin
fun main() {
val number = 7
when (number) {
       1 -> {
        print("Missing")
       }  
       2..6 ->{
        print("Missing two...")
       } 
       7-> {
         print("Missing seven")
       }
}
```