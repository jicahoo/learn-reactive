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

* List是一种Monad:
  * https://en.wikipedia.org/wiki/List_(abstract_data_type)#The_list_monad 
  * List可以看作幺半群，元素就是List, 零元就是空List, 二元运算是append. 

## Related Topics:
* https://arild.github.io/csp-presentation/
