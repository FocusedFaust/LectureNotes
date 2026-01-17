
### `for...do`

⇒ `for` loops can be used to iterate over the elements of a collection.
⇒ The syntax is `for iterator <- collection do { ... }`
⇒ The syntax `p <- e` is the **generator** of the loop
⇒ It is possible to have multiple generators in a single loops, for example like this:
```scala
for
	i <- 1 to 10
	j <- 1 to 20
	k <- 'a' to 'b'
do
	println(s"i = $i, j = $j, k = $k")
```
which will increment the last loop first, like classic imbricated loops
⇒ Loops can also have as many guards as needed, meaning conditions in the loop definition.


### `while` loops

⇒ `while` loops syntax is `while condition do { ... }`
⇒ For example, 
```scala
var i = 0
while i < 3 do
	println(i)
	i += 1
```


### Variables

⇒ Variables in Scala are either `var`, which are **mutable** or `val`, which are **immutable**.
⇒ A `var` can be reassigned, where a `val` cannot and will cause a compiler error


### Given Instances

⇒ If there is a *single canonical value* for a specific type, it can be made available to the compiler with the keyword `given`
⇒ The syntax is `given Type = inst` and whenever a contextual parameter of type `Type` is omitted, the compiler will infer `inst` as an argument


### Using

⇒ Parameters can be marked as *contextual*, using the keyword `using`, which will tell the compiler to do term inference


### Summon

⇒ The `summon(using x: T)` transparent inline method, summons a `given` value of type `T`