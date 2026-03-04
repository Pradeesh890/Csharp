
## Value Types

This is mainly meant for storing simple values
### Examples
- `int`, `double`, `bool`, `char`
- `struct`
- `enum`
- `DateTime`
### Memory behavior
- Stored **directly** where the variable is created.
- Usually on the **stack** (simple explanation).
- **Copying creates a new independent value.**
### Example

```
int a = 10;
int b = a;  
b = 20;  
Console.WriteLine(a); // 10 
Console.WriteLine(b); // 20
```

Changing `b` **does NOT affect** `a`  
because each has **its own copy**

Instances are stored in **Stack** every time when a method is called , a new stack will be created 


## Reference Types

This is mainly meant for storing complex / large amount of values.
### Examples

- `class`
- `string`
- `array`
- `object`
- `delegate`

### Memory behavior

- Object stored on the **heap**.
- Variable stores **reference (address)** to the object.
- **Copying copies the reference**, not the object.

```
class Person
{
    public string Name;
}

Person p1 = new Person();
p1.Name = "Alice";

Person p2 = p1;   // copy reference, not object
p2.Name = "Bob";

Console.WriteLine(p1.Name); // Bob
Console.WriteLine(p2.Name); // Bob

```

Instance(objects) are stored in **"heap"**. Heap is only one for entire application.

