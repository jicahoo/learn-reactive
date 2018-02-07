# learn-reactive

## RxJava
* 响应式编程来自于前端开发。前端要时刻保持页面的响应性，而不能阻塞。RxJava用于Android开发，Node.js也源于前端语言JavaScript

## Netty
* 异步的事件驱动的网络应用框架
* Netty的核心的编程模型，不仅可以用于网络通信框架，也可以用于应用程序的构建，例如Vert.x就是基于Netty Core的。
* EventLoop Group包含几个EveentLoop。是个类似ExecutorService的事物。你可以向EventLoopGroup提交(event，Handler), Round-Robin分发给worker: EventLoop。每个EventLoop对应一个线程。无论是网络的select操作还是业务逻辑都是在这个EventLoop上执行的。业务逻辑怎么组织是通过PipeLine的一个链式结构。PileLine的每一节执行完成之后，会把后一节的逻辑提交到当前EventLoop的任务队列里，直到一环扣一环地完成整个Pipeline。这个设计和Akka的消息调度模式类似，当服务完某个Actor（信箱)之后，会继续把这个Actor在放入任务队列。一个Pipleine只能在同一个Eventloop上运行，不然的话，会有并发问题。Eventloop不可阻塞，阻塞操作需要专门的线程池，EventLoop线程的个数一般是n*Number(core).


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

## Java CompletableFuture, Promise  is Monad
* https://zeroturnaround.com/rebellabs/monadic-futures-in-java8/
* http://codingjunkie.net/completable-futures-part1/

## Function Prgrammming
* http://www.ruanyifeng.com/blog/2017/02/fp-tutorial.html 有不少错误，注意甄别。
* http://yinwang0.lofter.com/post/183ec2_b1afb9 王垠的对于面向对象和函数式编程的见解。
* https://halfrost.github.io/2016/07/%E5%87%BD%E6%95%B0%E5%93%8D%E5%BA%94%E5%BC%8F%E7%BC%96%E7%A8%8B(FRP)%E4%BB%8E%E5%85%A5%E9%97%A8%E5%88%B0-%E6%94%BE%E5%BC%83-%E5%9F%BA%E7%A1%80%E6%A6%82%E5%BF%B5%E7%AF%87/ 函数式编程的一些基本思想
* https://www.zhihu.com/question/20448295 如何学习范畴学
