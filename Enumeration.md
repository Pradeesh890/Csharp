Enumeration is a collection of constants.
Enumeration is used to specify the list of option allowed to be stored in a field / variable.

Use enumeration if you don't want to allow other developers to assign other value into a field / variable, other then the list of values specified in the enumeration.

```
public enum AgeGroupEnumeration
{
	Child,
	Teenagers,
	Adult,
	Senior
}
// this is struct


//in the main method while assining value
//lets say the class name is person

//person object

person pr = new person();
//ther is a field called as age
pr.age = AgeGroupEnumeration.Adult;
// this is how enumeration should be used

```

By default, an enum's underlying data type is `int`. The compiler assigns values to the members starting from `0` and incrementing by one.

