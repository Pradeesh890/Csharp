We use same Partial keyword for creating Partial Method

E.g.
partial void getname(){
//code block
}

Assume, There are two developers, the first developer develops the first partial class, second developer develop the second partial class.

The partial method lets the first developer the declare a partial method in one partial class, and the second developer implements the partial method in the other partial class

Partial methods can be only created in partial class or partial structs

Partial Methods are implicitly private. It cant have any other access modifier

Partial Methods can have only "Void" return type

Implementation of partial methods is optional, if there is no implementation of partial methods in any parts of the partial class , the method calls are removed by the compiler, at compilation time.

if you are building large class libraries and decide extension of methods to other developers, partial methods can be used.

