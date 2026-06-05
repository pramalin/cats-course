error id: file://<WORKSPACE>/src/main/scala/part1recap/Essentials.scala:
file://<WORKSPACE>/src/main/scala/part1recap/Essentials.scala
empty definition using pc, found symbol in pc: 
empty definition using semanticdb
empty definition using fallback
non-local guesses:
	 -Try.
	 -Try#
	 -Try().
	 -scala/Predef.Try.
	 -scala/Predef.Try#
	 -scala/Predef.Try().
offset: 1421
uri: file://<WORKSPACE>/src/main/scala/part1recap/Essentials.scala
text:
```scala
package part1recap



object Essentials {
    //  values
    val aBoolean: Boolean = false

    // expressions are EVALUATED to a value
    val anIfExpression = if (2 > 3) "bigger" else "smaller"

    // instructions vs expression
    val theUnit = println("Hello, Scala") // Unit = "void" in other languages

    // OOP
    class Animal
    class Cat extends Animal
    trait Carnivore {
        def eat(animal: Animal): Unit
    }

    // inheritance model: extend < 1 class, but inherit from >= 0 traits
    class Crocodile extends Animal with Carnivore {
        def eat(animal: Animal): Unit = println("Crunch!")
    }

    // singleton
    object MySingleton // singleton pattern in one line

    // companions
    object Carnivore // companion object of the class Carnivore

    // generics
    class MyList[A]

    // method notation
    val three = 1 + 2
    val anotherThree = 1.+(2)

    // functional programming
    val incrementer: Int => Int = x => x + 1
    val incremented = incrementer(45) // 46

    // HOF higher order functions
    // map, flatMap, filter
    val processedList = List(1,2,3).map(incrementer) // List(2,3,4)
    val aLongerList = List(1,2,3).flatMap(x => List(x, x+1)) // List(1,2, 2,3, 3,4)

    // options and try
    val anOption: Option[Int] = Option(/* something that might be null */ 3) // Some(3)
    val doubledOption: Option[Int] = anOption.map(_ * 2)

    val anAttempt = Tr@@y(0)

    def main(args: Array[String]): Unit = {

    
    }
}

```


#### Short summary: 

empty definition using pc, found symbol in pc: 