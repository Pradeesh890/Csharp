Delegate is a special object that stores the reference of a method.

"delegate type" is a "type" that represents methods that have specific parameters and return types.

```
public delegate ReturnType DelegateTypeName(params);
```

A Delegate can store the reference of one or more methods using Delegate.

Generally we can create a method inside a class and invoke that method through the object of the same class.
alternatively, we can store the store the method reference in the delegate and invoke that method using the delegate.

Delegates are mostly used to build events than directly used in the applications, we use delegates in real time application by only using events.

Delegates are created based on delegate type.
The delegate types are internally derived from a predefined parent class called system.delegates, as they are derived from a class they are internally not types but classes.

 There are two types of delegates
 1. Single cast delegates
 2. Multi cast delegates

### Single case delegates

* This type contains reference of only one method.
* when called, it directly invokes the referenced method.

### Multi cast delegates

* contains references of multiple methods.
* When called, it invokes all the reference methods, one by one in a sequence.
* All methods parameters and return type should be same.
* It is suggested not to pass any values while using multi cast delegates as it executes all the methods but we will be able to really access only the return value of the lastly executed method.

 