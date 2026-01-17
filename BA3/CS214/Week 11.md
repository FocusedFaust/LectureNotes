
### `try...catch...finally`

⇒ Scala, like Java, can handle and manage exception. The syntax is:
```scala
try
	{...}
catch
	case e: Exception => {...}
finally
	{...}
```


### Boundary

⇒ A `boundary` block can be exited by `break` calls. The name `boundary` establishes a scope and `break` leaves it and can optionally return a value.


### `@tailrec`

⇒ This method annotation verifies that the method will be compiled with tail call optimization. If it cannot be, the compiler issues an error.


### `getOrElseUpdate`

⇒ If the given key is already in the map, it will return the associated value. Otherwise, it will store the default value given.