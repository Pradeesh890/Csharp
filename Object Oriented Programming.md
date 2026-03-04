Object oriented programing is used for representing real world entity in the programs as classes and objects

all objects are created based on classes and stored in heap

for each application execution, a new heap will be created (only one is created).

the heap memory is common for all the classes and object created within a application

all the reference variables(local variables of methods) are stored n stack
for each method call, a new stack will be created

a method is a collection of statements to perform some operations or calculation 

classes support two access modifiers 

1. internal 
2. public

classes support four modifiers 

1. static
2. abstract
3. sealed
4. partial

objects stores actual data and can access methods of the class
but the methods are not stored in the heap

Every OOP has three key characteristics
1. Identity : Each object is unique entity, distinct from all other objects, even it they are of the same type and have the same data. when we create two different objects, they occupy different spaces in memory
2. state : This is the data or attributes that describe an "car" objects state would include its current "color", "current speed", "fuel level". the state is stored in fields (variables) within the object
3. Behavior : This is what an object can do .The behavior of a "car" object would be defined by its methods, such as "Accelerate()", "Break()", "Refuel()", These methods are typically used to modify the objects internal state.

inside the class private fields usually starts with _ (underscore due to naming convention).

A [[Field]] is a variable that is stored in the object

[[Encapsulation]] is a concept of bundling the data and the operation that manipulate the data together. this hides the internal implementation details of an object and provide a essential members to interacting with them.

The "This" keyword refers to "current object", which method has invoked the method.

the "This" keyword is available only within the "instance methods"

[[Instance methods]] are the non static methods

[[static methods]] are methods that declared with static modifier

whenever we want to manipulate the instance fields we use instance methods

whenever we want to manipulate the static fields we use static methods

whenever you assign a default value into the parameter of a method, that is called default argument.

it can be instance method or static method, if it has parameter we can assign it as default parameter.

:::::: syntax ::::::
```
accessmodifier modifier returntype methodname(parameter1 = defaultvalue)
{
	method body
}
```


parameter modifiers
1. default [no modifers]
2.  ref
3. out
4. in
5. params

default
 no change in the values when modified inside the method

ref
 it is giving the reference so the changes made inside the method will reflect outside variables also (use ref at both when calling and method declaration)

out
 when out is used the argument value will not be used to parameter when calling but the latest parameter value will the assigned to argument outside the method

 in
  when the argument value is passed to the parameter the value is passed but the parameter becomes readonly  it cannot be changed inside the method

params
 ![[Pasted image 20260203125937.png]]

### local function
local function is a function that created inside the method. ( or method inside the method but very small )
local function of one method cannot be called by another method

## Inheritance
Inheritance is important thing in OOPS
this allows classes to be arranged in a hierarchy that represent "is a type of relationship".
the "parent class" acts as a "base type" of "one or more child classes".
child classes are derived from parent class

A parent class can access parent class fields and methods
A child class can access child class fields and child class methods also it can access parent class fields and methods.

### Types of inheritance
1. single inheritance
2. multi level inheritance
3. hierarchical inheritance
4. multiple inheritance(only using interfaces)
5. Hybrid inheritance

#### Base Keyword
Base keyword is used for accessing the parent class methods using the child class object

it is optional to use, by default
it must to use when there is "name ambiguity" between parent class members and child class members.

### Method Hiding
this is a concept used to hide the parent class method by creating another method in the child class with the same name and the same parameters. the return type can be different.

### Method overriding
 It is a concept, which is used to extend the parent class method by creating another method in the child class with same name and same parameters
 ( use virtual in parent class method and override in the child class method 

### Sealed class and Sealed Method
The sealed keyword is used to limiting the inheritance of classes . If sealed modifier is used for any class then it become non inheritable so it limits other developers to not to inherit the sealed classes but we can create objects.
we can use the sealed methods in only the case of override methods
we can use the sealed method to prevent overriding that particular methods in the corresponding child classes

## Abstraction
Abstraction is a concept of representing objects in a simplified way by focusing only on the essential features and ignoring the irrelevant details.

it provides a blueprint or a contract for derived classes to follow ensuring consistency in your code

### Abstract Class
 Abstract class is a parent class for which we cannot create objects, but we can create child classes
The Main intention of abstract class is to provide common set of fields and methods to all of its child classes of a specific group

### Abstract Methods
Abstract methods are declared in parent class with "abstract" keyword, implemented in child classes, with "override" keyword

## Interfaces
 Interface is a set of abstract methods, that must be implemented by the child classes.
 ```
 syntax 
 
 interface interfacename
 {
	 ReturnDatatype Methodname(params);
 }
 
 class childclassname : interfacename
 {
	 public returndatatype MethodName(params){
		 //write your code
	 }
 }
 ```
It is the responsibility of child class to implement all the abstract methods that are declared in the abstract class

## Polymorphism
Polymorphism provides the ability to the developer. to define between implements for same methods in the same class or different class

The two types of polymorphism

1. Compile time polymorphism 
2. Run time polymorphism

### compile time polymorphism
Eg method overloading
Decision will be taken at compilation time
also know as "early binding" / "Static polymorphism"

### Run time polymorphism
Eg Method overriding
Decision will be taken at run time
also know as "late binding" / "Dynamic polymorphism"


