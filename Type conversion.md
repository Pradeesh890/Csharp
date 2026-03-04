![[Pasted image 20260203142321.png]]

implicit conversion is automated conversion of one type to another type : example below

```
sbyte a = 1;

double b;

b=a;

here automatically implicitly compiler changes the type
```

explicit casting is casting or conversion that is done by the users manually

""""""""syntax""""""""
```
(destinationDataType)sourceValue
```

this may lead to lossy conversion that is id the destination type is not sufficient enough to store the converted value, the value may loose.

we can do explicit casting the implicit casting, child class to parent class, 
section and also in below situations
![[Pasted image 20260203142935.png]]


#### Parsing
Parsing is used for converting string value into any numerical data type.

"""""""""""""syntax"""""""""""""

```
DestinationDataType.Parse(sourceValue)
```

but the source value must contain digits only, it shouldn't contain spaces, alphabets or special characters. if there are then it will raise an exception.

#### TryParse

It is same as the Parse but Tryparse will check whether the string can be converted into numerical type or not.

if yes then it will store the value in the out direction variable and return "true".

if it cannot be converted in to numerical type then it returns "false". and doesn't raise any exceptions.

""""""""""""""syntax""""""""""""'

```
bool variable = DestinationType.TryParse(sourceValue, out DestinationVariable);
```

Try parse avoids FormatException

### Conversion Methods

Conversion method is a pre defined method, which converts any primitive type (and also "string") to any other primitive type.

""""""""""""""""""syntax"""""""""""""""''

```
type destinationvariable = Convert.ConversionMethod(sourcevalue)
```

It raises "FormatException", if the source value is invalid.

for each data type, we have a conversion method.
All the conversion methods are static methods.

![[Pasted image 20260203145239.png]]

