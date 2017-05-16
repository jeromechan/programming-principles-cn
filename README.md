

# Programming Principles - Simplified Chinese 

# 编程准则 - 简体中文版

> 英文原版在这里：https://github.com/webpro/programming-principles

Every programmer benefits from understanding programming principles and patterns. This overview is a reference for myself, and I've just put it here. Maybe it is of help to you during design, discussion, or review. Please note that it's far from complete, and that you often need to make trade-offs between conflicting principles.

每一位开发者都可以从编程准则和模式的学习上获益。这一篇概览性质的参考资料是为自己总结的，现在把它分享在这里。或许它可以在设计、探讨、评审的过程中给予你帮助。不过也请您知晓，它距离完整还差很多，所以在平时使用的过程中，你需要自己去分辨这些编程准则之间的冲突与不同，以便更好地应用于实践当中。

The list was inspired by [The Principles of Good Programming](http://www.artima.com/weblogs/viewpost.jsp?thread=331531). I felt that the list closely, but not completely matches what I would personally put into something similar. Additionally, I wanted a bit more reasoning, details, and links to further resources. [Let me know](https://github.com/webpro/programming-principles/issues) if you have any feedback or suggestions for improvement.

这份列表的灵感来源于这篇文章[The Principles of Good Programming](http://www.artima.com/weblogs/viewpost.jsp?thread=331531)。我感觉到这篇文章描述的内容与本篇非常地相似，但是和我想要阐述的却是相近而不相同。所以额外的，我希望在这些准则的阐述过程中，包含更多的关于应用原因、细节的描述以及深入解读的资料超链接。如果你有建议或者有问题需要反馈，可以提issues给我[Let me know](https://github.com/webpro/programming-principles/issues)。

## Contents

### Generic 

### 通用

* [KISS (Keep It Simple Stupid)](#kiss)
* [KISS准则 (保持简单和傻瓜式)](#KISS准则)
* [YAGNI (You aren't gonna need it)](#yagni)
* [YAGNI准则 (直到你使用之前都不要实现它)](#YAGNI准则)
* [Do The Simplest Thing That Could Possibly Work](#do-the-simplest-thing-that-could-possibly-work)
* [做最简单最可能实现的事情](#做最简单最可能实现的事情)
* [Separation of Concerns](#separation-of-concerns)
* [关注点分离](#关注点分离)
* [Keep Things DRY](#keep-things-dry)
* [DRY原则 (不要重复你所做过的事情)](#DRY原则)
* [Code For The Maintainer](#code-for-the-maintainer)
* [编写可维护的代码](#编写可维护的代码)
* [Avoid Premature Optimization](#avoid-premature-optimization)
* [避免过度过早优化](#避免过度过早优化)
* [Boy-Scout Rule](#boy-scout-rule)
* [美国童子军准则](#美国童子军准则)

### Inter-Module/Class

### 内部模块/类

* [Minimise Coupling](#minimise-coupling)
* [低耦合](#低耦合)
* [Law of Demeter](#law-of-demeter)
* [迪米特法则](#迪米特法则)
* [Composition Over Inheritance](#composition-over-inheritance)
* [组合优于继承](#组合优于继承)
* [Orthogonality](#orthogonality)
* [正交性](#正交性)
* [Robustness Principle](#Robustness Principle)
* [健壮性原则](#健壮性原则)

### Module/Class

### 模块/类

* [Maximise Cohesion](#maximise-cohesion)
* [高内聚](#高内聚)
* [Liskov Substitution Principle](#liskov-substitution-principle)
* [里氏替换原则](#里氏替换原则)
* [Open/Closed Principle](#openclosed-principle)
* [开闭原则](#开闭原则)
* [Single Responsibility Principle](#single-responsibility-principle)
* [单一职责原则](#单一职责原则)
* [Hide Implementation Details](#hide-implementation-details)
* [隐藏实现细节](#隐藏实现细节)
* [Curly's Law](#curlys-law)
* [科里定律](#科里定律)
* [Encapsulate What Changes](#encapsulate-what-changes)
* [封装性](#封装性)
* [Interface Segregation Principle](#interface-segregation-principle)
* [接口隔离原则](#接口隔离原则)
* [Command Query Separation](#command-query-separation)
* [命令查询职责分离](#命令查询职责分离)

## KISS

## KISS准则

Most systems work best if they are kept simple rather than made complex.

如果能够保持系统简单复杂性低，那么大多数的系统都可以运行的很好。

Why

为什么？

* Less code takes less time to write, has less bugs, and is easier to modify.
* 更少的代码可以花费更少的编码时间、更少的bugs、更容易去修改。
* Simplicity is the ultimate sophistication.
* 简洁的就是最好最复杂的。
* It seems that perfection is reached not when there is nothing left to add, but when there is nothing left to take away.
* 完美度不仅表示已经没有什么需要新增，而且也表示着没有什么需要剔除。

Resources

更多资料

* [KISS principle](http://en.wikipedia.org/wiki/KISS_principle)
* [Keep It Simple Stupid (KISS)](http://principles-wiki.net/principles:keep_it_simple_stupid)

## YAGNI

## YAGNI准则

YAGNI stands for "you aren't gonna need it": don't implement something until it is necessary.

YAGNI英文描述为 “you aren't gonna need it”：直到使用之前都不要去实现它。

Why

为什么？

* Any work that's only used for a feature that's needed tomorrow, means losing effort from features that need to be done for the current iteration.
* 任何只用于明天所需要的功能的工作，意味着从当前所需要的功能中减去相应的工作量。
* It leads to code bloat; the software becomes larger and more complicated.
* 意味着代码变得臃肿，软件变得更大更复杂。

How

怎么办？

* Always implement things when you actually need them, never when you just foresee that you need them.
* 只有在你真正需要的时候才去实现它，而不是根据你对于未来的估算和预测。

Resources

更多资料

* [You Arent Gonna Need It](http://c2.com/xp/YouArentGonnaNeedIt.html)
* [You’re NOT gonna need it!](http://www.xprogramming.com/Practices/PracNotNeed.html)
* [You ain't gonna need it](http://en.wikipedia.org/wiki/You_ain't_gonna_need_it)

## Do The Simplest Thing That Could Possibly Work

## 做最简单最可能实现的事情

Why

为什么？

* Real progress against the real problem is maximized if we just work on what the problem really is.
* 如果我们努力解决问题的真正原因，那么对真正问题的积极进展就会被最大化。

How
怎么办？

* Ask yourself: "What is the simplest thing that could possibly work?"
* 常常询问自己：“最简单最根本的事情是什么？”

Resources

更多资料

* [Do The Simplest Thing That Could Possibly Work](http://c2.com/xp/DoTheSimplestThingThatCouldPossiblyWork.html)

## Separation of Concerns

## 关注点分离

Separation of concerns is a design principle for separating a computer program into distinct sections, such that each section addresses a separate concern. For example the business logic of the application is a concern and the user interface is another concern. Changing the user interface should not require changes to business logic and vice versa.

关注点分离，是将计算机程序分成不同部分的设计原则，使每个部分都涉及到单独的问题。 例如，应用程序的业务逻辑是一个问题，用户界面是另一个问题。 更改用户界面不应要求对业务逻辑进行更改，反之亦然。

Quoting [Edsger W. Dijkstra](https://en.wikipedia.org/wiki/Edsger_W._Dijkstra) (1974):

引证 [Edsger W. Dijkstra](https://en.wikipedia.org/wiki/Edsger_W._Dijkstra) (1974):

> It is what I sometimes have called "the separation of concerns", which, even if not perfectly possible, is yet the only available technique for effective ordering of one's thoughts, that I know of. This is what I mean by "focusing one's attention upon some aspect": it does not mean ignoring the other aspects, it is just doing justice to the fact that from this aspect's point of view, the other is irrelevant.
> 通常意义上所谈到的“关注点分离”，或许不是完全可能，我所知道的是它依然更多地依赖于个人对于事情场景的观点和想法。其实我所更想提及的是“把一个人的焦点放在某一个方面”：这并不意味着要忽略其他的方面，只是更多地期望能在关注的方面或者说角度上，找到根本的原因和事实，而不是其它不相关的部分。

Why

为什么？

* Simplify development and maintenance of software applications.
* 简化软件应用的开发和维护工作。
* When concerns are well-separated, individual sections can be reused, as well as developed and updated independently.
* 当关注点得到很好的分离，单独的部分可以被重用，那么开发和更新工作也将是相互独立的。

How

怎么办？

* Break program functionality into separate modules that overlap as little as possible.
* 将程序按照功能拆分为不同的模块，使之具备更低的重复率。

Resources

更多资料

* [Separation of Concerns](https://en.wikipedia.org/wiki/Separation_of_concerns)

## Keep things DRY

## DRY原则

Every piece of knowledge must have a single, unambiguous, authoritative representation within a system.

在一个系统内，每一项知识点的表现必须是单一的，明确无歧义的，具备权威性的。

Each significant piece of functionality in a program should be implemented in just one place in the source code. Where similar functions are carried out by distinct pieces of code, it is generally beneficial to combine them into one by abstracting out the varying parts.

源代码中的每一项重要的程序功能只应该出现在一个地方。当我们遇到不同的代码段实现了相类似的功能，通常地，我们把不同的部分抽象出来，然后把相同的部分放在公共层，以实现更高的复用性。

Why

为什么？

* Duplication (inadvertent or purposeful duplication) can lead to maintenance nightmares, poor factoring, and logical contradictions.
* 重复代码（有意或无意的重复）会引发维护上的噩梦、较差的因果关系、逻辑矛盾。
* A modification of any single element of a system does not require a change in other logically unrelated elements.
* 一个系统内单一元素的修改不涉及其他逻辑关联的元素的变更。
* Additionally, elements that are logically related all change predictably and uniformly, and are thus kept in sync.
* 另，逻辑相关的元素的变化需要具有可预见性和一致性的，即需要保持同步性。

How

怎么办？

* Put business rules, long expressions, if statements, math formulas, metadata, etc. in only one place.
* 将业务规则、长表达式、条件语句、数学公式、元数据等放置到同一个地方。
* Identify the single, definitive source of every piece of knowledge used in your system, and then use that source to generate applicable instances of that knowledge (code, documentation, tests, etc).
* 在系统的识别出每个知识点的单一来源，然后将这些知识点并应用于相同场景的实例当中（代码、文档、测试用例等）。
* Apply the [Rule of three](http://en.wikipedia.org/wiki/Rule_of_three_(computer_programming)).
* 遵循规则[Rule of three](http://en.wikipedia.org/wiki/Rule_of_three_(computer_programming))。

Resources

更多资料

* [Dont Repeat Yourself](http://c2.com/cgi/wiki?DontRepeatYourself)
* [Don't repeat yourself](http://en.wikipedia.org/wiki/Don't_repeat_yourself)
* [Don't Repeat Yourself](http://programmer.97things.oreilly.com/wiki/index.php/Don't_Repeat_Yourself)

Related

引用

* [Abstraction principle](http://en.wikipedia.org/wiki/Abstraction_principle_(computer_programming))
* [Once And Only Once](http://c2.com/cgi/wiki?OnceAndOnlyOnce) is a subset of DRY (also referred to as the goal of refactoring).
* [Single Source of Truth](http://en.wikipedia.org/wiki/Single_Source_of_Truth)
* A violation of DRY is [WET](http://thedailywtf.com/articles/The-WET-Cart) (Write Everything Twice)

## Code For The Maintainer

## 编写可维护的代码

Why

为什么？

* Maintenance is by far the most expensive phase of any project.
* 维护阶段是一个项目生命周期当中最为昂贵的阶段。

How

怎么办？

* *Be* the maintainer.
* *成为*一个维护者。
* Always code as if the person who ends up maintaining your code is a violent psychopath who knows where you live.
* 常常作出假设，假设你的代码维护者是一个有精神暴力倾向的并且知道你住处的人。
* Always code and comment in such a way that if someone a few notches junior picks up the code, they will take pleasure in reading and learning from it.
* 在编码和注释的时候，时长以阅读者的角度去考虑，考虑他们是否会爱上阅读和学习你的成果。
* [Don't make me think](http://www.sensible.com/dmmt.html).
* 以常识和简洁的角度去说明事情关键，不要让读者去想太多。[Don't make me think](http://www.sensible.com/dmmt.html).
* Use the [Principle of Least Astonishment](http://en.wikipedia.org/wiki/Principle_of_least_astonishment).
* 遵循准则[Principle of Least Astonishment](http://en.wikipedia.org/wiki/Principle_of_least_astonishment).

Resources

更多资料

* [Code For The Maintainer](http://c2.com/cgi/wiki?CodeForTheMaintainer)
* [The Noble Art of Maintenance Programming](http://blog.codinghorror.com/the-noble-art-of-maintenance-programming/)

## Avoid Premature Optimization

## 避免过度过早优化

Quoting [Donald Knuth](http://en.wikiquote.org/wiki/Donald_Knuth):

引用 [唐纳德·克努斯](http://en.wikiquote.org/wiki/Donald_Knuth):

> Programmers waste enormous amounts of time thinking about, or worrying about, the speed of noncritical parts of their programs, and these attempts at efficiency actually have a strong negative impact when debugging and maintenance are considered. We should forget about small efficiencies, say about 97% of the time: premature optimization is the root of all evil. Yet we should not pass up our opportunities in that critical 3%.
> 程序员花费极大的时间去思考、担心哪些程序里非关键部位的运行速度，而这种种在调试、维护上的工作效能方面常常引发了负面的影响。我们应该摒弃那些花费了97%时间去做的低效能的事情。过早的优化是所有邪恶的根源。不管怎样，我们不能放弃那3%关键部分的机会。


Understanding what is and isn’t "premature" is critical of course.

对于是否属于“过早的优化”，这是一项关键的课程。

Why

为什么？

* It is unknown upfront where the bottlenecks will be.
* 过早优化会引发未来不可知的瓶颈的发生。
* After optimization, it might be harder to read and thus maintain.
* 优化之后，它或许变得更加难以阅读和维护。

How

怎么办？

* [Make It Work Make It Right Make It Fast](http://c2.com/cgi/wiki?MakeItWorkMakeItRightMakeItFast)
* [使之具备可行性、正确性、快速性](http://c2.com/cgi/wiki?MakeItWorkMakeItRightMakeItFast)
* Don't optimize until you need to, and only after profiling you discover a bottleneck optimise that.
* 只有在你需要的时候才去优化，只有在做了瓶颈分析之后再去做实际的优化。

Resources

更多资料

* [Program optimization](http://en.wikipedia.org/wiki/Program_optimization)
* [Premature Optimization](http://c2.com/cgi/wiki?PrematureOptimization)

## Boy-Scout Rule

## 美国童子军准则

The Boy Scouts of America have a simple rule that we can apply to our profession: "Leave the campground cleaner than you found it". The boy-scout rule states that we should always leave the code cleaner than we found it.

美国童子军有一项简单的准则：“离开野营区之时保证要比自己来的时候更加干净”。我们可以将这一准则应用在计算机方面：“时常迫使代码比我们发现它的时候更整洁更清晰”。

Why

为什么？

* When making changes to an existing codebase the code quality tends to degrade, accumulating technical debt. Following the boyscout rule, we should mind the quality with each commit. Technical debt is resisted by continuous refactoring, no matter how small.
* 当我们对现有代码库作修改之时，现有代码库质量低并且积累了许多的技术债务。根据美国童子军准则，我们理应关心每一次提交的代码质量，而技术债务也应该在持续的重构过程中逐渐变少。

How

怎么办？

* With each commit make sure it does not degrade the codebase quality.
* 保证每一次的提交不会造成代码库的代码质量的降级。
* Any time someone sees some code that isn't as clear as it should be, they should take the opportunity to fix it right there and then.
* 任何时间，任何人，只要发现了代码可以变得更为清晰和整洁，那么他就应该寻找机会去实现它。

Resources

更多资料

* [Opportunistic Refactoring](http://martinfowler.com/bliki/OpportunisticRefactoring.html)

## Minimise Coupling

## 低耦合

Coupling between modules/components is their degree of mutual interdependence; lower coupling is better. In other words, coupling is the probability that code unit "B" will "break" after an unknown change to code unit "A".

耦合度指的是模块/组件之间的相互依赖程度。耦合度越低则越好。换句话说，耦合度高会导致代码单元“B”因为代码单元“A”的一个未知变更而被打断。

Why

为什么？

* A change in one module usually forces a ripple effect of changes in other modules.
* 一个模块的变更会迫使和波及其他的模块也需要发生相应的变更。
* Assembly of modules might require more effort and/or time due to the increased inter-module dependency.
* 模块集成过程中会涉及更多的修改、更多的时间，正是因为模块内的相互依赖复杂度的升高。
* A particular module might be harder to reuse and/or test because dependent modules must be included.
* 一个指定的模块将变得难以重用和测试，正是因为其依赖的其他模块也必须被包含进来。
* Developers might be afraid to change code because they aren't sure what might be affected.
* 开发者会害怕修改代码，因为他们不确定具体有多少方面会被涉及。

How

怎么办？

* Eliminate, minimise, and reduce complexity of necessary relationships.
* 尽可能多地，甚至消除复杂必须的关联关系。
* By hiding implementation details, coupling is reduced.
* 隐藏了实现的细节之后，耦合性往往会被降低。
* Apply the [Law of Demeter](#law-of-demeter).
* 遵循迪米特法则[Law of Demeter](#law-of-demeter).

Resources

更多资料

* [Coupling](http://en.wikipedia.org/wiki/Coupling_(computer_programming))
* [Coupling And Cohesion](http://c2.com/cgi/wiki?CouplingAndCohesion)

## Law of Demeter

## 迪米特法则

Don't talk to strangers.

不要告诉陌生人。

Why

为什么？

* It usually tightens coupling
* 依赖往往会增加耦合度。
* It might reveal too much implementation details
* 依赖会露出过多的实现细节。

How

怎么办？

A method of an object may only call methods of:

一个对象的一个方法，只能调用如下内容：

  1. The object itself.
  2. 对象本身。
  1. An argument of the method.
  2. 方法参数。
  1. Any object created within the method.
  2. 方法内所创建的对象。
  1. Any direct properties/fields of the object.
  2. 对象内直接包含的属性、字段。

Resources

更多资料

* [Law of Demeter](http://en.wikipedia.org/wiki/Law_of_Demeter)
* [The Law of Demeter Is Not A Dot Counting Exercise](http://haacked.com/archive/2009/07/14/law-of-demeter-dot-counting.aspx/)

## Composition Over Inheritance

## 组合优于继承

Why

为什么？

* Less coupling between classes.
* 降低类之间的耦合。
* Using inheritance, subclasses easily make assumptions, and break LSP.
* 使用继承、子类会易于出现断言，并且打破里氏替换原则。

How

怎么办？

* Test for LSP (substitutability) to decide when to inherit.
* 根据里氏替换原则，判断什么时候使用继承。
* Compose when there is a "has a" (or "uses a") relationship, inherit when "is a".
* 若是"has a" (或者"uses a")关系的时候使用组合，若是"is a"关系则使用继承。

Resources

更多资料

* [Favor Composition Over Inheritance](http://blogs.msdn.com/b/thalesc/archive/2012/09/05/favor-composition-over-inheritance.aspx)

## Orthogonality

## 正交性

> The basic idea of orthogonality is that things that are not related conceptually should not be related in the system.
> 正交性的基本定义是，系统内概念不相同的部分，不应该形成关联和依赖。

Source: [Be Orthogonal](http://www.artima.com/intv/dry3.html)

引用: [Be Orthogonal](http://www.artima.com/intv/dry3.html)

> It is associated with simplicity; the more orthogonal the design, the fewer exceptions. This makes it easier to learn, read and write programs in a programming language. The meaning of an orthogonal feature is independent of context; the key parameters are symmetry and consistency.
> 它与简单性有关，设计的时候正交性越高，则异常发生地越少。这通常会使得代码变得更加容易学习、阅读和编写，无论你使用的是哪一种编程语言。正交性的一个典型特征是上下文之间互相没有依赖，核心参数之间会保持对称性和一致性。

Source: [Orthogonality](http://en.wikipedia.org/wiki/Orthogonality_(programming))

引用: [Orthogonality](http://en.wikipedia.org/wiki/Orthogonality_(programming))

## Robustness Principle

## 健壮性原则

> Be conservative in what you do, be liberal in what you accept from others
> 对内保持保守，对外保持自由。

Collaborating services depend on each others interfaces. Often the interfaces need to evolve causing the other end to receive unspecified data. A naive implementation refuses to collaborate if the received data does not strictly follow the specification. A more sophisticated implementation will still work ignoring the data it does not recognize.

协作服务依赖于各式各样的接口。通常地，接口的演变会致使另外一端接收到未指定的数据。倘若数据结构没有遵循规范，那么一个简单的不健壮的实现会遭到拒绝。一个健壮的实现会主动忽略不可识别的数据，继而持续工作。

Why

为什么？

* In order to be able to evolve services you need to ensure that a provider can make changes to support new demands while causing minimal breakage to their existing clients.
* 为了使得程序服务得以演进，你需要确保提供者程序可以支持新的指令，尽管这些指令可能会对现有的客户端所导致的小面积破坏。

How

怎么办？

* Code that sends commands or data to other machines (or to other programs on the same machine) should conform completely to the specifications, but code that receives input should accept non-conformant input as long as the meaning is clear.
* 发送给其他机器（或者相同机器的其他程序）的指令或者数据的代码理应完全遵循指定的规范，但是接收方需要能够接收和处理不符合规范，但含义清晰的数据或指令。

Resources

更多资料

* [Robustness Principle in Wikipedia](https://en.wikipedia.org/wiki/Robustness_principle)
* [Tolerant Reader](http://martinfowler.com/bliki/TolerantReader.html)

## Maximise Cohesion

## 高内聚

Cohesion of a single module/component is the degree to which its responsibilities form a meaningful unit; higher cohesion is better.

一个单一模块/组件的内聚性指的是它的职责形成了有具体含义的独立单元。内聚性自然越高也好。

Why

为什么？

* Increased difficulty in understanding modules.
* 增加了模块理解的难度。
* Increased difficulty in maintaining a system, because logical changes in the domain affect multiple modules, and because changes in one module require changes in related modules.
* 增加了维护系统的成本消耗。因为一个方面的逻辑变更会引发其它多个关联模块需要同时发生变更。
* Increased difficulty in reusing a module because most applications won’t need the random set of operations provided by a module.
* 增加了程序重用的难度。因为大多数的程序不需要模块所提供的随机操作。

How

怎么办？

* Group related functionalities sharing a single responsibility (e.g. in a class).
* 一组相似的功能共享使用一个单一的职责（例如在一个类里）。

Resources

更多资料

* [Cohesion](http://en.wikipedia.org/wiki/Cohesion_(computer_science))
* [Coupling And Cohesion](http://c2.com/cgi/wiki?CouplingAndCohesion)

## Liskov Substitution Principle

## 里氏替换原则

The LSP is all about expected behavior of objects:

里氏替换原则是关于对象预期行为方面的描述：

> Objects in a program should be replaceable with instances of their subtypes without altering the correctness of that program.
> 程序内的对象理应可以被它的子类所无缝替换，此间不需要作任何的程序订正操作。

Resources

更多资料

* [Liskov substitution principle](http://en.wikipedia.org/wiki/Liskov_substitution_principle)
* [The Liskov Substitution Principle](http://freshbrewedcode.com/derekgreer/2011/12/31/solid-javascript-the-liskov-substitution-principle/)

## Open/Closed Principle

## 开闭原则

Software entities (e.g. classes) should be open for extension, but closed for modification. I.e. such an entity can allow its behavior to be modified without altering its source code.

软件实体（例如类）理应对扩展开放，对修改关闭。例如一个实体可以允许它的动作不需要经过修改源码而发生的演变。

Why

为什么？

* Improve maintainability and stability by minimizing changes to existing code.
* 在现有代码发生最小化改变的前提下，改善和提高可维护性和稳定性。

How

怎么办？

* Write classes that can be extended (as opposed to classes that can be modified).
* 编写可以被扩展的类（而不是类文件被修改）。
* Expose only the moving parts that need to change, hide everything else.
* 只暴露那些需要修改以支持扩展的部分，其余的部分都隐藏。

Resources

更多资料

* [Open Closed Principle](http://en.wikipedia.org/wiki/Open/closed_principle)
* [SOLID JavaScript: The Open/Closed Principle](http://freshbrewedcode.com/derekgreer/2011/12/19/solid-javascript-the-openclosed-principle/)

## Single Responsibility Principle

## 单一职责原则

A class should never have more than one reason to change.

一个类不应该包含多于一个职责。

Long version: Every class should have a single responsibility, and that responsibility should be entirely encapsulated by the class. Responsibility can be defined as a reason to change, so a class or module should have one, and only one, reason to change.

长文字版本：每一个类都应该有一个职责，而这个职责应该被这个类所内聚。职责被定义为发生改变的一个原因，即一个类或者模块有且仅有一个原因会致使其发生演变。

Why

为什么？

* Maintainability: changes should be necessary only in one module or class.
* 可维护性：变更只应该出现在一个模块或者一个类当中。

How

怎么办？

* Apply [Curly's Law](#Curly-s-Law).
* 遵循[科里定律](#科里定律).

Resources

更多资料

* [Single responsibility principle](http://en.wikipedia.org/wiki/Single_responsibility_principle)

## Hide Implementation Details

## 隐藏实现细节

A software module hides information (i.e. implementation details) by providing an interface, and not leak any unnecessary information.

一个软件模块应该隐藏一些信息（例如实现细节），仅提供一个接口即可，以确保不泄露任何不必要的信息。

Why

为什么？

* When the implementation changes, the interface clients are using does not have to change.
* 当实现细节需要发生变更之时，接口消费方可以无缝使用而不需要作出任何变更。

How

怎么办？

* Minimize accessibility of classes and members.
* 最小化类及其成员的可访问性。
* Don’t expose member data in public.
* 不要暴露成员数据在public域。
* Avoid putting private implementation details into a class’s interface.
* 杜绝将私有的实现细节放置到类的接口层上。
* Decrease coupling to hide more implementation details.
* 降低模块间耦合性，隐藏更多的不必要的实现细节。

Resources

更多资料

* [Information hiding](http://en.wikipedia.org/wiki/Information_hiding)

## Curly's Law

## 科里定律

Curly's Law is about choosing a single, clearly defined goal for any particular bit of code: Do One Thing.

科里定律是关于如何为任一特定代码段选择一项单一的、定义明确的目标的一项法则：只作一件事。

* [Curly's Law: Do One Thing](http://blog.codinghorror.com/curlys-law-do-one-thing/)
* [The Rule of One or Curly’s Law](http://fortyplustwo.com/2008/09/06/the-rule-of-one-or-curlys-law/)

## Encapsulate What Changes

## 封装性

A good design identifies the hotspots that are most likely to change and encapsulates them behind an API. When an anticipated change then occurs, the modifications are kept local.

一项好的设计意味着某些很有可能被修改和内聚的热点部分被隐藏在API的后方。当预期的变更出现时，这些变更也只需要在内部作出调整即可。

Why

为什么？

* To minimize required modifications when a change occurs
* 当变更发生时，可以最小化变更的涉及面。

How

怎么办？

* Encapsulate the concept that varies behind an API
* 在API内部封装多样化的概念。
* Possibly separate the varying concept into its own module
* 尽可能地从多样化的概念中，分隔出独立的单一模块。

Resources

更多资料

* [Encapsulate the Concept that Varies](http://principles-wiki.net/principles:encapsulate_the_concept_that_varies)
* [Encapsulate What Varies](http://blogs.msdn.com/b/steverowe/archive/2007/12/26/encapsulate-what-varies.aspx)
* [Information Hiding](https://en.wikipedia.org/wiki/Information_hiding)

## Interface Segregation Principle

## 接口隔离原则

Reduce fat interfaces into multiple smaller and more specific client specific interfaces. An interface should be more dependent on the code that calls it than the code that implements it. 

降低接口的粒度，使得接口更小更具体，更接近调用方的现实需要。一个接口的定义更多地应该依赖于调用方的代码，而不是实现方可以实现的细节。

Why

为什么？

* If a class implements methods that are not needed the caller needs to know about the method implementation of that class. For example if a class implements a method but simply throws then the caller will need to know that this method shouldn't actually be called.
* 如果一个类的实现方法已经被废弃，那么调用方理应需要知晓这个类的实现方法的具体实现细节。例如，假设一个类的实现方法仅仅是抛出了一个异常，那么调用方需要知道这个方法不应该再被调用。

How

怎么办？

* Avoid fat interfaces. Classes should never have to implement methods that violate the [Single responsibility principle](#single-responsibility-principle).
* 杜绝肥胖的接口存在。一个类的实现方法的设计不应该违背[单一职责原则](#single-responsibility-principle).

Resources

更多资料

* [Interface segregation principle](https://en.wikipedia.org/wiki/Interface_segregation_principle)

## Command Query Separation

## 命令查询职责分离（也称Command Query Responsibility Segregation，CQRS）

The Command Query Separation principle states that each method should be either a command that performs an action or a query that returns data to the caller but not both. Asking a question should not modify the answer.

命令查询职责分离准则的具体阐述可以参见资料所引述到的Martin Fowler的文章。命令查询职责分离原则指出，每个方法应该是执行一个操作的命令（命令是void的，不返回任何结果，但会改变对象的状态）或者一个查询（返回结果，但是不会改变对象的状态，对系统没有副作用），它将数据返回给调用者，而不是两者。提出问题不应该修改答案。

With this principle applied the programmer can code with much more confidence. The query methods can be used anywhere and in any order since they do not mutate the state. With commands one has to be more careful.

使用这条准则，程序员在编码之时可以更加自信，查询方法可以在任何地方以任意次序使用，因为它不会影响到对象状态。而命令则需要更加小心谨慎。

Why

为什么？

* By clearly separating methods into queries and commands the programmer can code with additional confidence without knowing each method's implementation details.
* 基于清晰地将方法分隔为查询和命令两大阵营之后，程序员在编码方面更加自信了，因为他们可以不需要去了解每个方法的实现具体细节。

How

怎么办？

* Implement each method as either a query or a command
* 方法设计之时，要么是查询，要么是命令，不可二者兼备。
* Apply naming convention to method names that implies whether the method is a query or a command
* 针对方法名的命名上作约定和规范，使得方法名上可以直接表露出它具体是查询还是命令。

Resources

更多资料

* [Command Query Separation in Wikipedia](https://en.wikipedia.org/wiki/Command%E2%80%93query_separation)
* [Command Query Separation by Martin Fowler](http://martinfowler.com/bliki/CommandQuerySeparation.html)
* [Introduction CQRS](http://www.cnblogs.com/yangecnu/p/Introduction-CQRS.html)


