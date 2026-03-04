Array is a group of multiple values of same type.
Arrays are stored in continuous memory locations in 'heap'

```
type[] arrayreferencename = new type[size];
```

foreach loop give slower performance, due to it treats everything as a collection.
it can't be used to execute repeatedly, without arrays or collections.
it can't read part of array / collection, or read array / collection reverse.

Every array is treated as object for System.Array class
The System.Array class provides a set of properties and methods for every array.

Those are :

IndexOf
 The IndexOf method performs linear search, That means it searched all the elements of an array, until the search values is found. when the search value is found in the array, it stops searching and returns its index, if not found it returns -1.Due to the linear search the performance is not good for large arrays.

BinarySearch:
 The BinarySearch requires an array, which is already sorted. for unsorted arrays binary search cannot be used.

Clear:
 This method starts with the given index and sets all the "length" no. of the elements to zero(0). this has three parameters (array, index and length)

Resize:
 This method is used to increase or decrease the size of the array. this has two parameters (array, newsize).

Sort:
 Sort method will sort the elements of the array in the ascending order.

Reverse:
 Reverse methods is used for reversing the array.

Multi dimensional array
 Stores the elements in rows and columns format.
 Every rom contains a series of elements.
 We can create arrays with two or more dimensions, by increasing the no of commands (,).

Jagged Arrays
 Jagged array is an "array of arrays". The main difference between multi dimensional arrays and jagged arrays is multi dimensional arrays require same number of rows and columns and jagged arrays don't. The member arrays can be of any size.


#### Array of objects
Array of objects is nothing but arrays with objects in it example below

```
using System;
using System.Configuration;

class Employee
{
    public int EmpID;
    public string Name;

    public void Display()
    {
        Console.WriteLine("Employee ID: " + EmpID);
        Console.WriteLine("Employee Name: " + Name);
    }
}

class Program
{
    static void Main()
    {
        Employee emp1 = new Employee() { EmpID = 101, Name = "John Doe" };
        Employee emp2 = new Employee() { EmpID = 102, Name = "Jane Smith" };
        Employee emp3 = new Employee() { EmpID = 103, Name = "Alice Johnson" };

        Employee[] employees = new Employee[] { emp1, emp2, emp3 };

        foreach (Employee emp in employees)
        {
            if (emp.EmpID == 102)
            {
                Console.WriteLine("Employee with ID 102 found:");
            }
            emp.Display();
            Console.WriteLine();
        }
    }
}
```


