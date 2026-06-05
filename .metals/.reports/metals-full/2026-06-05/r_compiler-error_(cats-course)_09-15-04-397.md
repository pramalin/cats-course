error id: 15698112FF2CB4CCEA52EE9FCD6EE875
file://<WORKSPACE>/src/main/scala/part1recap/Essentials.scala
### java.lang.AssertionError: assertion failed: file://<WORKSPACE>/src/main/scala/part1recap/Essentials.scala: 676 >= 676

occurred in the presentation compiler.



action parameters:
offset: 676
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
        def eat(animal: Animal): Unit = println()""
    }

    def main(args: Array[String]): Unit = {

    
    }
}
@@
```


presentation compiler configuration:
Scala version: 2.13.16
Classpath:
<WORKSPACE>/.bloop/cats-course/bloop-bsp-clients-classes/classes-Metals-v6nCef6rTuWmhfCZXW8R7Q== [exists ], <HOME>/.cache/bloop/semanticdb/com.sourcegraph.semanticdb-javac.0.11.2/semanticdb-javac-0.11.2.jar [exists ], <HOME>/.cache/coursier/v1/https/repo1.maven.org/maven2/org/scala-lang/scala-library/2.13.16/scala-library-2.13.16.jar [exists ], <HOME>/.cache/coursier/v1/https/repo1.maven.org/maven2/org/typelevel/cats-core_2.13/2.1.1/cats-core_2.13-2.1.1.jar [exists ], <HOME>/.cache/coursier/v1/https/repo1.maven.org/maven2/org/typelevel/cats-macros_2.13/2.1.1/cats-macros_2.13-2.1.1.jar [exists ], <HOME>/.cache/coursier/v1/https/repo1.maven.org/maven2/org/typelevel/cats-kernel_2.13/2.1.1/cats-kernel_2.13-2.1.1.jar [exists ]
Options:
-language:higherKinds -Yrangepos -Xplugin-require:semanticdb




#### Error stacktrace:

```
scala.reflect.internal.util.SourceFile.position(SourceFile.scala:34)
	scala.tools.nsc.CompilationUnits$CompilationUnit.position(CompilationUnits.scala:136)
	scala.meta.internal.pc.SignatureHelpProvider.signatureHelp(SignatureHelpProvider.scala:26)
	scala.meta.internal.pc.ScalaPresentationCompiler.$anonfun$signatureHelp$1(ScalaPresentationCompiler.scala:434)
	scala.meta.internal.pc.CompilerAccess.retryWithCleanCompiler(CompilerAccess.scala:182)
	scala.meta.internal.pc.CompilerAccess.$anonfun$withSharedCompiler$1(CompilerAccess.scala:155)
	scala.Option.map(Option.scala:242)
	scala.meta.internal.pc.CompilerAccess.withSharedCompiler(CompilerAccess.scala:154)
	scala.meta.internal.pc.CompilerAccess.$anonfun$withNonInterruptableCompiler$1(CompilerAccess.scala:132)
	scala.meta.internal.pc.CompilerAccess.$anonfun$onCompilerJobQueue$1(CompilerAccess.scala:209)
	scala.meta.internal.pc.CompilerJobQueue$Job.run(CompilerJobQueue.scala:152)
	java.base/java.util.concurrent.ThreadPoolExecutor.runWorker(ThreadPoolExecutor.java:1136)
	java.base/java.util.concurrent.ThreadPoolExecutor$Worker.run(ThreadPoolExecutor.java:635)
	java.base/java.lang.Thread.run(Thread.java:840)
```
#### Short summary: 

java.lang.AssertionError: assertion failed: file://<WORKSPACE>/src/main/scala/part1recap/Essentials.scala: 676 >= 676