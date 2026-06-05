error id: 1708AA283F7B4614A3350CA045ABCBCB
file://<WORKSPACE>/src/main/scala/part1recap/Implicits.scala
### java.lang.IndexOutOfBoundsException: -1 is out of bounds (min 0, max 2)

occurred in the presentation compiler.



action parameters:
offset: 1942
uri: file://<WORKSPACE>/src/main/scala/part1recap/Implicits.scala
text:
```scala
package part1recap

object Implicits {

    // implicit classes
    case class Person(name: String) {
        def greet: String = s"Hi, my name is $name!"
    }

    implicit class ImpersonableString(name: String) {
        def greet: String = Person(name).greet
    }

/*
    val impersonableString = new ImpersonableString("Peter")
    impersonableString.greet
*/
    val greeting = "Peter".greet // new ImpersonableString(Peter).greet

    // importing implicit conversions in scope
    import scala.concurrent.duration._
    val oneSec = 1.second

    // implicit arguments and values
    def increment(x: Int)(implicit amount: Int) = x + amount
    implicit val defaultAmount = 10
    val incremented2 = increment(2) // implicit argument 10 is passed by the compiler

    def multiply(x: Int)(implicit times: Int) = x * times
    val times2 = multiply(2)

    // more complex example
    trait JSONSerializer[T] {
        def toJson(value: T): String
    }

    def listToJson[T](list: List[T])(implicit serializer: JSONSerializer[T]): String =
         list.map(value => serializer.toJson(value)).mkString("[", ",", "]")

    implicit val personSerializer: JSONSerializer[Person] = new JSONSerializer[Person] {
        override def toJson(person: Person) = 
            s"""
{"name" : "${person.name}}"}
""".stripMargin
    }

    val personsJson = listToJson(List(Person("Alice"), Person("Bob")))
    // implicit argument is used to PROVE THE EXISTENCE of a type


    // implicit methods
    implicit def oneArgCaseClassSerializer[T <: Product]: JSONSerializer[T] = new JSONSerializer[T] {
        override def toJson(value: T) =
            s"""
"${value.productElementName(0)}" : "${value.productElement(0)}"
""".stripMargin
    }

    case class Cat(name: String)

    def main(args: Array[String]) : Unit = {
        println(oneArgCaseClassSerializer[Cat].toJson(C@@))
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
	scala.reflect.internal.Definitions$DefinitionsClass.$anonfun$getMemberIfDefined$1(Definitions.scala:1502)
	scala.reflect.internal.Definitions$DefinitionsClass.getMemberIfDefined(Definitions.scala:1502)
	scala.reflect.internal.Definitions$DefinitionsClass.getMember(Definitions.scala:1440)
	scala.reflect.internal.Definitions$DefinitionsClass.getMemberMethod(Definitions.scala:1476)
	scala.reflect.internal.Definitions$DefinitionsClass.Product_productPrefix(Definitions.scala:887)
	scala.tools.nsc.typechecker.SyntheticMethods.synthesize$1(SyntheticMethods.scala:264)
	scala.tools.nsc.typechecker.SyntheticMethods.$anonfun$addSyntheticMethods$49(SyntheticMethods.scala:440)
	scala.reflect.internal.Trees.deriveTemplate(Trees.scala:2039)
	scala.reflect.internal.Trees.deriveTemplate$(Trees.scala:2037)
	scala.reflect.internal.SymbolTable.deriveTemplate(SymbolTable.scala:28)
	scala.tools.nsc.typechecker.SyntheticMethods.addSyntheticMethods(SyntheticMethods.scala:443)
	scala.tools.nsc.typechecker.SyntheticMethods.addSyntheticMethods$(SyntheticMethods.scala:70)
	scala.meta.internal.pc.MetalsGlobal$MetalsInteractiveAnalyzer.addSyntheticMethods(MetalsGlobal.scala:85)
	scala.tools.nsc.typechecker.Typers$Typer.finishMethodSynthesis(Typers.scala:2036)
	scala.tools.nsc.typechecker.Typers$Typer.typedClassDef(Typers.scala:1972)
	scala.tools.nsc.typechecker.Typers$Typer.typed1(Typers.scala:6251)
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