# learn-reactive

## Coroutine:
* https://stackoverflow.com/questions/553704/what-is-a-coroutine
* https://en.wikipedia.org/wiki/Coroutine
## Tips
* Functional programming and Reactive Programming are different things.
* https://www.quora.com/What-is-difference-between-Functional-Reactive-Programming-Functional-Programming-and-Reactive-Programming
* Closure is functional: https://softwareengineering.stackexchange.com/questions/235175/are-closures-considered-impure-functional-style
## Reactive streams
* https://blog.redelastic.com/a-journey-into-reactive-streams-5ee2a9cd7e29

## Monad
* https://www.quora.com/Is-a-monad-really-a-monoid-in-the-category-of-endofunctors
* https://bartoszmilewski.com/
* http://adit.io/posts/2013-04-17-functors,_applicatives,_and_monads_in_pictures.html
* https://en.wikipedia.org/wiki/Natural_transformation
* https://en.wikipedia.org/wiki/Category_(mathematics)
* http://learnyouahaskell.com/
* A monoid in the category of endofunctors.
  * 自函子构成的范畴，对象是自函子，态射是自然变换.
  * 这个范畴满足一定的性质，能在这个范畴中，构造出幺半群，这个构造出的幺半群就是一个Monad，单子。
  * 如何构造这个Monad, 选取一个自函子，
* 在数学中和函数式编程语言中, monad的定义不完全一致？
  * 数学中，monad是自函子加上两个自然变换。https://en.wikipedia.org/wiki/Monad_(category_theory)
  * 编程语言中，monad是一个类型构造器加上两个操作:unit和bind.
* 二元运算的结合性有什么好处，可以任意组合，以便并行化：https://www.safaribooksonline.com/blog/2013/05/15/monoids-for-programmers-a-scala-example/
* List是一种Monad:
  * https://en.wikipedia.org/wiki/List_(abstract_data_type)#The_list_monad 
  * List可以看作幺半群，元素就是List, 零元就是空List, 二元运算是append. 
## 高阶函数
* 什么是高阶函数？函数式编程中，函数是一等公民，函数可以作为参数，也可以作为返回值。函数式编程，最重要的一个思想，就是大的函数由小的函数组合而来，以达到重用的目标，所以，而高阶函数，就是组合函数的一个手段，入参里有函数，返回是组合了入参函数的新函数。
## 函数的组合
* https://www.sumologic.com/blog/code/3-tips-for-writing-performant-scala/ .map().filter()... 这些函数目标并不是每调用一个函数就产生一个中间结果，如果是那样的话，肯定耗内存。他要做的是 f(g(x)) 变为 f*g (x)， 要的是f*g， 能够把函数组合起来，到最好需要计算的时候，直接调用这个被组合的函数。所谓，函数编程。

## map和foldLeft
* https://stackoverflow.com/questions/2293592/functional-programming-scala-map-and-fold-left
* map: List(f(a1),f(a2),f(a3),...)
* foldLeft: f(...(f(f(f(b0,a1), a2),a3)...,an)
## Nil是个好东西
* Nil是List中的零元。Nil:::list == list:::Nil
* 有人说，罗马数没有零，所以，罗马人的数学没有阿拉伯人的好。因为零的引入，让某些计算简单很多。Nil的地位就像0,让你的程序更加流畅
* Example: http://exercism.io/submissions/7ed7e1daec4a419fba6b6ac9c2425cdc (scala-grade-school)
* Nulla 意大利语 代表0
## referential transparency
## Related Topics:
* https://arild.github.io/csp-presentation/
