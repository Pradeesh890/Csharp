Structure is a "type", similar to "class", which can contain fields, methods, parameterized constructor, properties and events.

```
struct StructureName{
	fields
	methods
	parameterized constructors
	properties
	events
	
}

class program{
	static void main(){
		structureName referencevariable;
		
	}
}

```

to access the structure we use structure reference or structure variable or structure instance. but those are not called as "Objects"

we cannot create objects for structures
we can only create objects based on "class"

structure doesn't support user defined parameter less constructor and also destructor

structure doesn't support any type inheritance

the structures are just type (like an array but for different data types)

structures are faster than classes, as its instances are stored in stack.

C# provides a parameter less constructor for every structure by default, which initializes all fields

you can also create one or more user defined parameterized constructors in structure

each parameterized constructor must initializer all fields, otherwise it will be compiler time error

the "new" keyword use with structure, doesn't create any object / allocate any memory in heap; it is just a syntax to call constructor of structure.

## Read only structures

We can use readonly structures in case of all these below:

* All fields are readonly
* all properties have only "get" accessors (readonly properties)
* there is a parameterized constructor that initializes all the fields
* you don't want to allow others to change any field or property of the structure
* methods can read fields but can't modify
* they work faster than normal structures because of only read operation


### Primitive types are structures

for example, "sbyte" is a primitive type, which is equivalent to "System.SByte" (can also written as 'SByte') structure

![[Pasted image 20260206150214.png]]

