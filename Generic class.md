Generic class is a class, which contains one or more "Type Parameters".

While declaring generic class you must pass any data type (standard data type / structure / class),
while creating object for the generic class.

E.g.
```
ClassName<int> referenceVariable = new ClassName<int> ();
```

we should use same data type in both the sides.

 The same field may belong to different data types, w.r.t. different object of the same class.

you will decide the data type of the field, while creating the object, rather than while creating field in the class.

it helps you in code reuse, performance and type-safety.

you can create your own generic classes, generic methods, generic interfaces and generic-delegates.

you can create generic collection classes
	The .Net framework class library contains many new generic collection classes in System.Collections.Generic namespace.


## Generic Constants

Generic Constants are the expectation or restrictions on the generic parameters

you will apply the generic constraints based on a specific generic parameter.

Generic constraints are used to specify the types allowed to be accepted in the "generic type parameter".

where T : class
where T : struct
where T : ClassName
where T : InterfaceName
where T : new()

## Generic Methods

Generic Method is a methods that has one or more generic parameters.

by using the generic methods we can restrict what type of data types (class names) allowed to be passed while creating object.

