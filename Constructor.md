Constructors are the special method of class, which contains initialization logic of fields

the main two objective of the constructor is to initialize the fields of the class and also do some initialization if available

"""""""""""""""syntax"""""""""""""
```

accessmodifier modifier classname(parameters){

}

```

Rules for creating constructor
1. constructors name should be same as class name.
2. constructor is recommended to be "public" member or "internal" member.
3. constructor can have one or more parameters
4. constructor cannot return any value, so no return type.

"This" keyword ca be used within the constructor like method for initializing the values of the class

the only difference between instance constructor and static constructor is instance constructor is created without static modifier and static constructor has static modifier

instance constructor executes automatically every time when a new object is created for the class

static constructor executes only once , i.e. when first object is created for the class or when the class is accessed for the first time during the execution of main method.

instance constructor is private by default. but the access modifiers can be changed.

static constructors are public by default and the access modifier cannot be changed.


## Constructor overloading

writing multiple constructor with same name in the class, with different set of parameter just like "method overloading".

It is recommended to write a parameter less constructor in the class, in case of constructor overloading.

### Object initializer

Special syntax to initialize fields / properties of class, along with creating the object.

This executes only after the constructor.
It is only for initialization of fields / properties, after creating object. it can't have any initialization logic

