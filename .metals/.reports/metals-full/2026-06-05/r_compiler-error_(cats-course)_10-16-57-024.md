error id: BA7EE177A1FD1D2A3356425C9F47064F
file://<WORKSPACE>/src/main/scala/part1recap/Essentials.scala
### java.lang.IndexOutOfBoundsException: -1 is out of bounds (min 0, max 2)

occurred in the presentation compiler.



action parameters:
offset: 2395
uri: file://<WORKSPACE>/src/main/scala/part1recap/Essentials.scala
text:
```scala
package part1recap

import scala.util.Try
import scala.concurrent.ExecutionContext
import java.util.concurrent.Executors
import scala.concurrent.Future



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

    val anAttempt = Try(/* something that might throw */ 42) // Success(42)
    val aModifiedAttempt = anAttempt.map(_ + 10)

    // pattern matching
    val anUnknown: Any = 45
    val ordinal = anUnknown match {
        case 1 => "first"
        case 2 => "second"
        case _ => "unknown"
    }

    val optionDescription: String = anOption match {
        case Some(value) => s"the option is not empty: $value"
        case None => "the option is empty"
    }    

    // Futures
    implicit val ec: ExecutionContext = ExecutionContext.fromExecutorService(Executors.newFixedThreadPool(4))
    //val aFuture = Future(42)
    val aFuture = {
        /* code block */
        42
    }

    // wait for completion (async)
    aFuture.onComplete {
        case Success(value) => println(s"The async meaning of life $value")
        case Failure(exception) => p@@
    }

    def main(args: Array[String]): Unit = {

    
    }
}

```


presentation compiler configuration:
Scala version: 2.13.16
Classpath:
<WORKSPACE>/.bloop/cats-course/bloop-bsp-clients-classes/classes-Metals-v6nCef6rTuWmhfCZXW8R7Q== [exists ], <HOME>/.cache/bloop/semanticdb/com.sourcegraph.semanticdb-javac.0.11.2/semanticdb-javac-0.11.2.jar [exists ], <HOME>/.cache/coursier/v1/https/repo1.maven.org/maven2/org/scala-lang/scala-library/2.13.16/scala-library-2.13.16.jar [exists ], <HOME>/.cache/coursier/v1/https/repo1.maven.org/maven2/org/typelevel/cats-core_2.13/2.1.1/cats-core_2.13-2.1.1.jar [exists ], <HOME>/.cache/coursier/v1/https/repo1.maven.org/maven2/org/typelevel/cats-macros_2.13/2.1.1/cats-macros_2.13-2.1.1.jar [exists ], <HOME>/.cache/coursier/v1/https/repo1.maven.org/maven2/org/typelevel/cats-kernel_2.13/2.1.1/cats-kernel_2.13-2.1.1.jar [exists ]
Options:
-language:higherKinds -Yrangepos -Xplugin-require:semanticdb




#### Error stacktrace:

```
scala.collection.generic.CommonErrors$.indexOutOfBounds(CommonErrors.scala:23)
	scala.collection.mutable.ArrayBuffer.apply(ArrayBuffer.scala:102)
	scala.reflect.internal.Types$Type.findMemberInternal$1(Types.scala:1030)
	scala.reflect.internal.Types$Type.findMember(Types.scala:1035)
	scala.reflect.internal.Types$Type.memberBasedOnName(Types.scala:661)
	scala.reflect.internal.Types$Type.nonPrivateMember(Types.scala:632)
	scala.tools.nsc.typechecker.Infer$Inferencer.followApply(Infer.scala:643)
	scala.tools.nsc.typechecker.Infer$Inferencer$InferMethodAlternativeTwice$1.followType(Infer.scala:1505)
	scala.tools.nsc.typechecker.Infer$Inferencer$InferMethodAlternativeTwice$1.rankAlternatives(Infer.scala:1508)
	scala.tools.nsc.typechecker.Infer$Inferencer$InferMethodAlternativeTwice$1.$anonfun$bestForExpectedType$2(Infer.scala:1512)
	scala.tools.nsc.typechecker.Infer$Inferencer$InferMethodAlternativeTwice$1.bestForExpectedType(Infer.scala:1512)
	scala.tools.nsc.typechecker.Infer$Inferencer$InferMethodAlternativeTwice$1.tryOnce(Infer.scala:1525)
	scala.tools.nsc.typechecker.Contexts$Context$TryTwice.$anonfun$apply$1(Contexts.scala:538)
	scala.tools.nsc.typechecker.Contexts$Context$TryTwice.apply(Contexts.scala:606)
	scala.tools.nsc.typechecker.Infer$Inferencer.inferMethodAlternative(Infer.scala:1529)
	scala.tools.nsc.typechecker.Typers$Typer.handleOverloaded$1(Typers.scala:3728)
	scala.tools.nsc.typechecker.Typers$Typer.doTypedApply(Typers.scala:3732)
	scala.tools.nsc.typechecker.Typers$Typer.$anonfun$typed1$28(Typers.scala:5195)
	scala.tools.nsc.typechecker.Typers$Typer.silent(Typers.scala:703)
	scala.tools.nsc.typechecker.Typers$Typer.tryTypedApply$1(Typers.scala:5195)
	scala.tools.nsc.typechecker.Typers$Typer.normalTypedApply$1(Typers.scala:5283)
	scala.tools.nsc.typechecker.Typers$Typer.typedApply$1(Typers.scala:5296)
	scala.tools.nsc.typechecker.Typers$Typer.typed1(Typers.scala:6288)
	scala.tools.nsc.typechecker.Typers$Typer.typed(Typers.scala:6344)
	scala.tools.nsc.typechecker.Typers$Typer.computeType(Typers.scala:6433)
	scala.tools.nsc.typechecker.Namers$Namer.assignTypeToTree(Namers.scala:1085)
	scala.tools.nsc.typechecker.Namers$Namer.inferredValTpt$1(Namers.scala:1732)
	scala.tools.nsc.typechecker.Namers$Namer.valDefSig(Namers.scala:1745)
	scala.tools.nsc.typechecker.Namers$Namer.memberSig(Namers.scala:1930)
	scala.tools.nsc.typechecker.Namers$Namer.typeSig(Namers.scala:1880)
	scala.tools.nsc.typechecker.Namers$Namer$ValTypeCompleter.completeImpl(Namers.scala:898)
	scala.tools.nsc.typechecker.Namers$LockingTypeCompleter.complete(Namers.scala:2077)
	scala.tools.nsc.typechecker.Namers$LockingTypeCompleter.complete$(Namers.scala:2075)
	scala.tools.nsc.typechecker.Namers$TypeCompleterBase.complete(Namers.scala:2070)
	scala.reflect.internal.Symbols$Symbol.completeInfo(Symbols.scala:1583)
	scala.reflect.internal.Symbols$Symbol.info(Symbols.scala:1548)
	scala.reflect.internal.Symbols$Symbol.initialize(Symbols.scala:1747)
	scala.tools.nsc.typechecker.Typers$Typer.typed1(Typers.scala:5916)
	scala.tools.nsc.typechecker.Typers$Typer.typed(Typers.scala:6344)
	scala.tools.nsc.typechecker.Typers$Typer.typedStat$1(Typers.scala:6422)
	scala.tools.nsc.typechecker.Typers$Typer.$anonfun$typedStats$10(Typers.scala:3547)
	scala.tools.nsc.typechecker.Typers$Typer.typedStats(Typers.scala:3547)
	scala.tools.nsc.typechecker.Typers$Typer.typedTemplate(Typers.scala:2133)
	scala.tools.nsc.typechecker.Typers$Typer.typedModuleDef(Typers.scala:2009)
	scala.tools.nsc.typechecker.Typers$Typer.typed1(Typers.scala:6252)
	scala.tools.nsc.typechecker.Typers$Typer.typed(Typers.scala:6344)
	scala.tools.nsc.typechecker.Typers$Typer.typedStat$1(Typers.scala:6422)
	scala.tools.nsc.typechecker.Typers$Typer.$anonfun$typedStats$10(Typers.scala:3547)
	scala.tools.nsc.typechecker.Typers$Typer.typedStats(Typers.scala:3547)
	scala.tools.nsc.typechecker.Typers$Typer.typedPackageDef$1(Typers.scala:5925)
	scala.tools.nsc.typechecker.Typers$Typer.typed1(Typers.scala:6254)
	scala.tools.nsc.typechecker.Typers$Typer.typed(Typers.scala:6344)
	scala.tools.nsc.typechecker.Analyzer$typerFactory$TyperPhase.apply(Analyzer.scala:126)
	scala.tools.nsc.Global$GlobalPhase.applyPhase(Global.scala:483)
	scala.tools.nsc.interactive.Global$TyperRun.applyPhase(Global.scala:1370)
	scala.tools.nsc.interactive.Global$TyperRun.typeCheck(Global.scala:1363)
	scala.tools.nsc.interactive.Global.typeCheck(Global.scala:681)
	scala.meta.internal.pc.WithCompilationUnit.<init>(WithCompilationUnit.scala:24)
	scala.meta.internal.pc.WithSymbolSearchCollector.<init>(PcCollector.scala:356)
	scala.meta.internal.pc.PcDocumentHighlightProvider.<init>(PcDocumentHighlightProvider.scala:12)
	scala.meta.internal.pc.ScalaPresentationCompiler.$anonfun$documentHighlight$1(ScalaPresentationCompiler.scala:527)
	scala.meta.internal.pc.CompilerAccess.withSharedCompiler(CompilerAccess.scala:148)
	scala.meta.internal.pc.CompilerAccess.$anonfun$withInterruptableCompiler$1(CompilerAccess.scala:92)
	scala.meta.internal.pc.CompilerAccess.$anonfun$onCompilerJobQueue$1(CompilerAccess.scala:209)
	scala.meta.internal.pc.CompilerJobQueue$Job.run(CompilerJobQueue.scala:152)
	java.base/java.util.concurrent.ThreadPoolExecutor.runWorker(ThreadPoolExecutor.java:1136)
	java.base/java.util.concurrent.ThreadPoolExecutor$Worker.run(ThreadPoolExecutor.java:635)
	java.base/java.lang.Thread.run(Thread.java:840)
```
#### Short summary: 

java.lang.IndexOutOfBoundsException: -1 is out of bounds (min 0, max 2)