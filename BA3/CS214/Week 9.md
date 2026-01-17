
### Dependent function types

⇒ Function types may be dependent on the function's parameter values
⇒ For example, we can define a database with a generic `trait Key {type Value}`. When we define objects of type `Key`, we define the type of the value, such that `object Name extends Key {type Value = String}` for example. What this means is that we create a type `Value` but don't give its definition in upper classes, only in lower ones. We don't have to equate it to an already existing type, we could create it.
⇒ Then, dependent methods return a value with its type dependent on the definition of the object they are applied to.
⇒ Dependent function types would be such:
```scala
type DB = (k: Key) => Option[k.Value]
```


### Copying

⇒ Case classes can create shallow copies of instances by using the `copy` method, that can also change constructor arguments.
⇒ The syntax is `val e2 = e1.copy(param = value)`
