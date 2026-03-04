Static methods are associated with class

The intention of static methods is to manipulate static fields

these methods are declared with static keyword

static methods doesn't need object for accessing the method they are accessed using the class name
but while calling static class inside the same class, 
class name is not required

static methods can only access the static fields unlike the instance methods which can access both type of fields but we can create an object inside the static method and through that we can access the instance fields

cant access the instance methods, but can access static methods only but can create object inside the method and access the instance method

static methods cannot use "this" keyword as there is no "current object" while calling the static methods
