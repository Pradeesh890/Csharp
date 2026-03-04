property is a composite member of a class.

the main goal of the property is that receive the incoming  values and check the incoming value is valid or not and assign the value into corresponding field only when it is valid

property has two accessor (get and set accessor)
property requires a private field by default

""""""""""""""""""syntax"""""""""""""'"'""
```
accessmodifier   type   PropertyName{
	set{
		field = value;     //set accessor
	}
	get{
		return field;
	}
}

```

''"""""""""""""""""""""""EXAMPLE'''''''''''''''''''''''''''''''''''''''

```
class car {
	private string _carBrand;
	
	public string CarBrand{
		set{
			this._carBrand = value;
		}
		get{
			return _carBrand;
		}
	}
}
```


The set accessor cannot have additional parameter than default parameter value for a field
also it cannot return any value

The get accessor cant have nay parameter and should return value of field.

Basically protection created a protection layer around fields, preventing assignment of invalid values into properties and also do some calculation automatically when someone has invoked the property.

no memory will be allocated for the property.

There are Readonly and Writeonly properties

The readonly contains only the get accessor and the write only contains only the set accessor.

## Auto property or Auto implemented properties

 we can initialize a value to the automatic property so it is called as auto property or auto implemented property.



# key points in properties

1. It is recommended to use properties always in real time projects.
2. you can also use auto properties to simplify code
3. properties doesn't occupy any memory also it copy the value.
4. property is a surrounding layer protecting the private fields
5. read only property has only the get accessor 
6. write only property has only the set accessor
7. set never return anything
8. get must return something
9. properties can't have additional parameters