It is pronounced as LINK

LINQ is a "uniform query syntax" that allows you to retrieve data from various data sources such as arrays, collections, databases, XML Files, with just one query syntax.

It helps us to write only one type of query to do the operations in all the type of database

For example lets say we have to get data from oracle database, sql database, XML Files and more, with LINQ we are able to write only one query to access all the databases

THE BENEFITS

Developer uses the same LINQ syntax to retrieve information from various data sources such as collections, SQL servers database, Entity framework DBSet's, ADO>NET datasets etc.

Errors in the LINQ query will be identified while compilation time / while writing the code in Visual Studio.

The list of properties of types are shown in VS intellisense while writing the LINQ Queries.

LINQ Extension methods are below
![[Pasted image 20260220123839.png]]

Most of these methods are given by **System.LINQ** namespace.

#### Order By

This is a LINQ Method that is used for sorting the list of object based on one specific property.

use "then by" in the below case

lets say that in a employee table you want to order by role there are several people with same role. if the role is same but you want to use their other parameter to order use then by if the role is same then it will order by name or any other parameter.

```
IEnumerable<Employee> el = emp.OrderBy(e => e.empJob).ThenBy(e => e.empName);
```

use "First" when you just the first value that passes the condition
"First" return object so no need for list or IEnumerable we can store it in a object variable and directly use it 

```
Employee firstmanager = emp.First(e => e.Job == manager);
```

now it will return the first object that passes the given condition not the list. if there are no elements that passes the condition it will return exception. it will crash the application in real time.

to solve this we use "FirstorDefault"

```
Employee firstmanager = emp.FirstorDefault(e => e.Job == manager);
```

when "FirstorDefault" is used it will return null if there are no true condition objects.

Also always check whether the reference object is null or not.

every exception will break the application if not handled properly

```
Employee firstmanager = emp.FirstorDefault(e => e.Job == manager);
if (firstmanager != null){
	console.writeline(firstmanager.empid);
}
else{
	console.writeline("No clerk in the list");
}
```


There is another thing called as Last() and LastOrDefault()

Last() is more like First() it checks what is the last element that passes the condition and returns that as an object, and return exception if no values satisfy the condition.

LastOrDefault() is like FirstOrDefault() it will return null if there are no values that satisfy the condition.

ElementAt() and ElementAtDefault() is used for returning a specific elements in the list we can use it with "Where" method like below

```
Employee el = emp.Where(e => e.empJob == "Manager").ElementAt(1);

Console.WriteLine($"ID: {el.empId}, Name: {el.empName}, Job: {el.empJob}, City: {el.empCity}, Salary: {el.salary}");
```

now the "el" will store the 1 index element from the list created by "where" where every object has "empJob" as Manager.

Single() or SingleOrDefault() it will work same like first() and firstofdefault() method. The difference is the "First()" method will return the first object in the list and "single()" method expects only one element to pass the given condition more than one object passes it will throw an exception. so we can use SingleOrDefault() and use "if else" to return the problem.

#### Select()
It will take each elements from the source list and generates a new object of the same type or different type.
in that way, based on every element, it forms a new object, and all those new objects will be collected as IEnumerable by default.

