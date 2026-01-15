
### Lazy Lists

⇒ The `LazyList` class introduces immutable linked lists that only compute their elements when those are needed. However, the value of each element is computed at most once.
⇒ Elements are computed in-order and never skipped.
⇒ An empty list may be infinite, for example `LazyList.from(0)` returns the set natural numbers, and some methods, when used on such an infinite list, will not terminate. 
⇒ The error `java.lang.RuntimeException: "LazyList evaluation depends on its own result [...]"` might happen when a LazyList's definition depends on itself, and on elements currently being evaluated.


### `#::`

⇒ This method constructs a LazyList with the first element followed by another LazyList.


### `#:::`

⇒ This method concatenates two LazyLists into a third one.


### By-name parameters

⇒ _By-name_ parameters are evaluated each time they are used, and are in contrast to _by-value_ parameters.
⇒ The syntax consists of prepending `=>` to the type of the parameter.
⇒ Example ([source](https://docs.scala-lang.org/tour/by-name-parameters.html)):
```scala
def whileLoop(condition: => Boolean)(body: => Unit): Unit =
  if condition then
    body
    whileLoop(condition)(body)

var i = 2

whileLoop (i > 0) {
  println(i)
  i -= 1
}  // prints 2 1
```
⇒ This can help performance if the parameter is computationally intensive to evaluate, as its evaluation is delayed until it is used.


### lazy val

⇒ The lazy evaluation of values is possible in Scala with the syntax `lazy val x = expr`
⇒ This means that the expression is only evaluated on its first access.
