error id: A96AF7EB43A0FFFC8F7CB952CDE13769
file://<WORKSPACE>/src/main/scala/part1recap/Essentials.scala
### scala.MatchError: implicit class <error> extends  (of class scala.reflect.internal.Trees$ClassDef)

occurred in the presentation compiler.



action parameters:
uri: file://<WORKSPACE>/src/main/scala/part1recap/Essentials.scala
text:
```scala
package part1recap

import scala.util.Try



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
    val anKnown: Any = 45
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
    implicit va


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
scala.tools.nsc.typechecker.Unapplies.constrParamss(Unapplies.scala:90)
	scala.tools.nsc.typechecker.Unapplies.factoryMeth(Unapplies.scala:155)
	scala.tools.nsc.typechecker.Unapplies.factoryMeth$(Unapplies.scala:152)
	scala.meta.internal.pc.MetalsGlobal$MetalsInteractiveAnalyzer.factoryMeth(MetalsGlobal.scala:85)
	scala.tools.nsc.typechecker.MethodSynthesis$MethodSynth.enterImplicitWrapper(MethodSynthesis.scala:238)
	scala.tools.nsc.typechecker.MethodSynthesis$MethodSynth.enterImplicitWrapper$(MethodSynthesis.scala:237)
	scala.tools.nsc.typechecker.Namers$Namer.enterImplicitWrapper(Namers.scala:58)
	scala.tools.nsc.interactive.InteractiveAnalyzer$InteractiveNamer.enterExistingSym(Global.scala:96)
	scala.tools.nsc.interactive.InteractiveAnalyzer$InteractiveNamer.enterExistingSym$(Global.scala:82)
	scala.tools.nsc.interactive.InteractiveAnalyzer$$anon$2.enterExistingSym(Global.scala:51)
	scala.tools.nsc.typechecker.Namers$Namer.standardEnterSym(Namers.scala:292)
	scala.tools.nsc.typechecker.AnalyzerPlugins.pluginsEnterSym(AnalyzerPlugins.scala:500)
	scala.tools.nsc.typechecker.AnalyzerPlugins.pluginsEnterSym$(AnalyzerPlugins.scala:499)
	scala.meta.internal.pc.MetalsGlobal$MetalsInteractiveAnalyzer.pluginsEnterSym(MetalsGlobal.scala:85)
	scala.tools.nsc.typechecker.Namers$Namer.enterSym(Namers.scala:266)
	scala.tools.nsc.typechecker.Typers$Typer.enterSym(Typers.scala:2054)
	scala.tools.nsc.typechecker.Typers$Typer.enterSyms(Typers.scala:2049)
	scala.tools.nsc.typechecker.Typers$Typer.typedTemplate(Typers.scala:2109)
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
	scala.meta.internal.pc.Compat.$anonfun$runOutline$1(Compat.scala:74)
	scala.collection.IterableOnceOps.foreach(IterableOnce.scala:619)
	scala.collection.IterableOnceOps.foreach$(IterableOnce.scala:617)
	scala.collection.AbstractIterable.foreach(Iterable.scala:935)
	scala.meta.internal.pc.Compat.runOutline(Compat.scala:66)
	scala.meta.internal.pc.Compat.runOutline(Compat.scala:35)
	scala.meta.internal.pc.Compat.runOutline$(Compat.scala:33)
	scala.meta.internal.pc.MetalsGlobal.runOutline(MetalsGlobal.scala:39)
	scala.meta.internal.pc.ScalaCompilerWrapper.compiler(ScalaCompilerAccess.scala:18)
	scala.meta.internal.pc.ScalaCompilerWrapper.compiler(ScalaCompilerAccess.scala:13)
	scala.meta.internal.pc.ScalaPresentationCompiler.$anonfun$semanticTokens$1(ScalaPresentationCompiler.scala:206)
	scala.meta.internal.pc.CompilerAccess.retryWithCleanCompiler(CompilerAccess.scala:182)
	scala.meta.internal.pc.CompilerAccess.$anonfun$withSharedCompiler$1(CompilerAccess.scala:155)
	scala.Option.map(Option.scala:242)
	scala.meta.internal.pc.CompilerAccess.withSharedCompiler(CompilerAccess.scala:154)
	scala.meta.internal.pc.CompilerAccess.$anonfun$withInterruptableCompiler$1(CompilerAccess.scala:92)
	scala.meta.internal.pc.CompilerAccess.$anonfun$onCompilerJobQueue$1(CompilerAccess.scala:209)
	scala.meta.internal.pc.CompilerJobQueue$Job.run(CompilerJobQueue.scala:152)
	java.base/java.util.concurrent.ThreadPoolExecutor.runWorker(ThreadPoolExecutor.java:1136)
	java.base/java.util.concurrent.ThreadPoolExecutor$Worker.run(ThreadPoolExecutor.java:635)
	java.base/java.lang.Thread.run(Thread.java:840)
```
#### Short summary: 

scala.MatchError: implicit class <error> extends  (of class scala.reflect.internal.Trees$ClassDef)