
### Upper type bounds

⇒ Type parameters can be constrained by **type bounds** that limit the value that these parameters can take
⇒ For *upper* bounds, the syntax `T <: A` declares that the type variable `T` must be a subtype of `A` (ex: Cat and Dog being a subtype of Pet)
⇒ If we try to create an instance with a type parameter outside of the bounds, the code does not compile

### Lower type bounds

⇒ A *lower* type bound has the syntax `B >: A` which means that `B` is a supertype of `A`
⇒ This is useful when used along with covariance, because it allows us to implement it more easily, for example in lists

### Variance

⇒ Variance is used to control how type parameters behave with subtyping
⇒ `[+A] // covariant`
	`[-A] // contravariant`
	`[A] // invariant`
⇒ **Invariance**: used by default, subtyping will not be reflected in the parameterized type. For example, a `Box[Cat]` and `Box[Animal]` can't have a subtyping relationship, even if `Cat` and `Animal` do
⇒ **Covariance**: given `class Cov[+T]`, this means that if `A` is a subtype of `B`, then `Cov[A]` is a subtype of `Cov[B]`
⇒ **Contravariance**: this is mostly used in serializers, and is the opposite of the covariance. Given `class Contra[-T]`, if `A` is a subtype of `B`, then `Contra[B]` is a subtype of `Contra[A]`

### Arrays

⇒ **Arrays** are a special kind of collection. They correspond to Java arrays, with the exception that Scala arrays can be generic. They are also compatible with Scala sequences and support sequences operations
⇒ The syntax is `Array[T]`

### Vectors

⇒ A **vector** is an indexed and immutable sequence, with the access time for any element by their index being constant, whereas `List` is not indexed. Vectors can be used in `for` loops
⇒ We can append or prepend elements to an existing vector and create a new vector with the `:+`, `++` and `+:`, `++:` methods

### Range

⇒ The `Range` class represents integer values in range \[start;end), with a step ≠ 0
⇒ The instanciation syntax is `start until end by step` for exclusive ranges, and `start to end by step` for inclusive ranges

### Seq

⇒ `Seq` is a trait implemented by most sequences in Scala, including Lists, Vectors, Ranges, ...
⇒ It is iterable and has many unimplemented methods to be redefined in subtypes

### Set

⇒ **Sets** are iterables with no duplicate elements. They behave like mathematical sets and are immutable (as always)

### `For ... yield`

⇒ This notation is used for **sequence comprehension** and has the form `for (enumerator) yield e`. The comprehension then evaluates the body `e` and returns a sequence of the values computed
⇒ This notation can be combined with conditions, in the form `for elem if cond yield e` where `e` will be evaluated only for elements of `elem` that satisfy the condition
⇒ It is possible to loop over a range, for example with `for i <- start until end yield ...`, and even over multiple ranges with conditions

### Postfix * (vararg)

⇒ When defining a method, we can add a postfix * to  the type of the last argument, like `def method(args: T*)` to say that the method can accept any number of arguments of type `T`. The `args` received will be an `Array[T]`

### Sorted and GroupBy

⇒ The `sorted(implicit ord: Ordering[B])` is a method to sort element in a stable way, according to an ordering
⇒ The `groupBy(f: A => K)` is a method to partition an iterable collection into a map of iterable collections according to some discrimination