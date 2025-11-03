
### Threads and par

⇒ Threads in Scala are directly based on Java's threading. 
⇒ The Scala standard library includes parallel collections to facilitate parallel programming. To do this on a list, for example, we just call `par` on it before doing our computations, which will be parallelized and much faster
⇒ There are also `ParArray`, `ParVector` and `ParRange` that might be useful

### Reduce

⇒ The reduce method takes a high-order function `A, A => A` as a parameter and combines all of its elements in pairs to yield only one element at the end
⇒ By default, it makes arbitrary pairs, but there exists `reduceLeft`, `reduceRight` and other methods

### ParArray

⇒ A `ParArray` is a sequence that holds an array of elements that can be accessed and updated efficiently by modifying the underlying array. They are very efficient