C# is a modern Object oriented programming language

.Net primarily use C#

the main features of .Net is 
- strongly typed
- garbage collection
- LINQ
- Async / Await
- Interfaces & inheritance

there is no such thing as global variable in C sharp

[[Object Oriented Programming]] is programmatic representation of a person or thing in real world.

![[Pasted image 20260202104712.png]]

Instance Fields get their memory allocated separately for each object, because instance fields are stored "inside" the objects.

Static Fields allocate their memory only once for the entire program; i.e. when the class is used for the first time while executing the program.

constant fields are like static fields, that are common to all object of the class.
we cannot change the value of constant field

constant fields are accessible with class name (not with object)

constant fields are not stored in the object; will not be stored anywhere

constant fields must be initialized, in line with declaration (with a literal value only)

ReadOnly fields are like instance fields, that is stored in every object, individually

we cant change the value of ReadOnly field

Readonly fields are accessible with reference variable [with object].

ReadOnly fields must be initialized, either "in line with declaration" or "in the constructor".

'""Syntax of readonly field'""
"""AccessModifier readonly datatype fieldname = value"""

[[Type conversion]] is used for converting one type of variable into another


[[Constructor]] is a special methods of class, which contains initialization logic of fields

[[Property]] is a composite member of the class which contains two accessors that is, set accessor and get accessor

[[Indexers]] are used for making the access of array within field.

[[Namespace]] is collection of classes

[[Partial Classes]] is class that splits into multiple files

[[Partial Methods]] is same as Partial class but it is done with Methods

[[static classes]] is a class than can contain only "static members".

*** Important ***
For instance or normal class the memory is allocated only when the object is created or called but for static classes the memory is allocated only for type that is used first and stored in sperate area in heap called as type's static storage (often called the loader heap/ type memory in CLR).


[[Enumeration]] is a collection of constants.

[[Value Types vs Reference Types]] difference between storing actual value and reference to the object in the memory.

[[Structures]] is a "type" similar to "class"

[[System.object]] class is super base class in .Net.

Boxing and Unboxing are conversion from value-type to reference-type and conversion from reference-type to value-type respectively

E.g.
int -> System.Object

in C# boxing is done automatically there is no need for any syntax.


 ```
 static void Main(){
	 int x = 10;
	 object oobj = x;
	 WriteLine(x);//output 10;
	 WriteLine(oobj);//output 10;
	 
 }
 ```

Unboxing is conversion of value from "reference type data type" to "value type data type".it is only done when they are compatible data types.

This should be done explicitly by below syntax.

```
(DestinationDataType)SourceValue

E.g.

(short)100
```

[[Generic class]] is a class which contain one or more 'type parameters'.

[[Null data]] Type in C sharp

[[Extension Methods]] are the methods that are written outside the class but injected logically inside a class

## Implicitly typed variables 
The variables that are declared with "var" keyword are called as "implicitly-types-variables" (a.k.a. type interference).

Implicitly types variables are declared without specifying the "type" explicitly, so that the C# compiler automatically identifies the appropriate data type at compilation time, based on the value assigned at the time of declaration.

```
var variableName = value;
```


## Dynamically typed variables

Dynamically typed variables are the variables that are declared with 'dynamic' keyword

Declared without specifying the type explicitly

there is no fixed type for the variable

 you can assign any type of value to these variables.
 
C# compiler skips "type checking" at compilation time, instead, it resolves the data types of its values, at run time.

## Garbage Collection
Garbage collection is a process of deleting objects from memory, to free-up memory, so the same memory can be re-used.

It not only does this at the end of the program execution, but also whenever the CLR needs some free space in order to create new objects, it may perform the garbage collection.

CLR automatically allocated memory  for all objects created anywhere in the application, whenever it encounters "new ClassName()" statement. This process is called as "memory management, which is done by "memory manager" component of CLR.

GC checks belongs information from the MSIL code
 > it collects references of an object
 > it identifies whether any object is referenced by static field

The object that has at least one living reference variable in any stack or static field, are "alive objects"; others are "dead objects" or "un used objects".

There is no specific timings to GC to get triggered.

GC automatically gets triggered in the following conditions

1. When the "heap" is full or free space is too low.
2. when we call GC.Collect() explicitly.

There are two types of resources
1. Managed Resources
2. Unmanaged Resources

The objects that are created by CLR are called as "Managed Resources"
The Managed Resources will participate in "Garbage Collection" process, which is a part of .Net Framework.

The objects that are not created by CLR and not managed by CLR are called as "Un-Managed resources".
E.g. File streams, Database connections

C# provides two methods for clearing the Unmanaged Resources.
1. Destructor 
2. Dispose Method

##### Destructor
 This Clears unmanaged resources just before deleting the object, i.e. generally at the end of the application execution. This will be automatically executed at the end of the program execution. Destructor is unique to its class. Destructor cannot have parameters or return values. Destructor is public by default, we cannot change its access modifiers.
 
##### Dispose
 This Clears unmanaged resources after the specific task(work) is completed, so no need to wait till end of application execution. the dispose method will be executed on demand. we have to call it explicitly.

#### IDisposable

The "IDisposable" interface of "system" namespace, has a methods called "Dispose", which is used to close un-managed resources that are created during the life-time of the object.

```
syntax

class ClassName : System.IDisposable{
	public void Dispose(){
		//close un managed resources here
	}
}
```

IDisposable need the system.idisposable to be inherited to use always.

This can be useful is large application where we access the databases and files, we open the files and databases in constructors and close that in the dispose method.

## Using Declaration

 We can prefix "using" keyword before the local variable declaration, in order to call "Dispose" methods when that variable goes out of scope.

```
public void Method(){
	using ClassName referenceVariable = new ClassName();
	
	// do work here
	
} //Dispose will be called automatically here
```


[[Delegates]] is a special object that stores the reference of a method.


[[Event]] is multi-cast delegate that stores one or more methods, and invoke them every time when the event is raised.

Anonymous Methods are "name-less methods", that can be invoked by using delegate variable or an event. these are used to invoke a method with very less amount of code.
Anonymous methods can be used anywhere within the method, to create methods instantly, without define a method at the class level.
The main advantage is that there is no need to create a "named method (normal method)" to quickly handle an event.
it can't be called without a delegate or event.
it can't contain jump statements like goto, break, continue.
it can access local variable and parameters of outer method.
it can be passed as a parameter to any methods; in this case, the delegate act as data type for the anonymous method
it can't access ref or out parameter of an outer method.

### lambda expressions
"lambda expression" are "nameless" methods that can be invoked by using the delegate variable or an event, much like anonymous methods.

#### Inline lambda expression
inline lambda expression are the lambda expression, which performs a small calculation or condition check and return as value.

inline lambdas can receive one or more arguments and must return a value .

The advantage it it provides more easier and convenient syntax to create smaller methods that performs a single calculation or condition check.

inline lambda expression cannot have local variables.

[[Arrays]] in C# are continues storage of same type elements.

[[Collections]] are standard way to store and manipulate group of elements.

### Anonymous Types
When we create an object with a set of properties along with values, automatically C# compiler creates a class (with a random name) with specified properties. It is called as "anonymous type" or "anonymous class".

### Tuple class
[[Tuples]] are used to store a set of  values.

[[LINQ]] the Language integrated Query
#### [[String]] is by default treated as objects of a predefined class called system.string

There is a predefined structure called datetime in C Sharp.

which includes year, month, date, 12- hour, 24-hours, minutes, seconds, milliseconds and tt (AM/PM).

to give exact date time as we give use below

```
DateTime dt = DateTime.ParseExact("31/12/2020 23:59:59,"dd/MM/yyy HH:mm:ss",System.Globalization.CultureInfo.InvariantCulture,System.Gloabalization.DateTimeStyles.None);
```


### Math class
There is a predefined static class called system.math

Pow(Value1 , value2 )
Min(value1 , value2 )
Max(value1 , value2 )
Floor(value)
ceiling(value)
Round(value)
Sign (value) -1 if negative, 0 if 0, 1 if positive
Abs (value)
DivRem(val1, val2, out)

## Encoding

Encoding is process of converting one type of character into another type.

We have ASCII and UTF-16 / Unicode

### ASCII character encoding

There is inbuilt function that can convert the bytes array into ASCII character and store it or return it as string

```
System.Text.Encoding.ASCII.GetString(array)
```

We can change the string into ASCII byte array by using below code

```
System.Text.Encoding.ASCII.GetBytes(string)
```

## System.IO

In C#, the **`System.IO`** namespace provides classes for working with files, directories, streams, memory, and data serialization. Below is a **complete structured guide** to IO operations available through `System.IO`, with explanations and syntax examples.

---

#  File Operations (`File` Class)

The `File` class provides **static methods** for working with files.

### Import

```csharp
using System.IO;
```

---

##  Create a File

```csharp
File.Create("file.txt");
```

Creates a new file. Returns a `FileStream`.

---

##  Write to a File

### Write All Text (Overwrite)

```csharp
File.WriteAllText("file.txt", "Hello World");
```

### Write All Lines

```csharp
string[] lines = { "Line1", "Line2" };
File.WriteAllLines("file.txt", lines);
```

### Append Text

```csharp
File.AppendAllText("file.txt", "New Content");
```

---

##  Read from a File

### Read All Text

```csharp
string content = File.ReadAllText("file.txt");
```

### Read All Lines

```csharp
string[] lines = File.ReadAllLines("file.txt");
```

### Read All Bytes

```csharp
byte[] data = File.ReadAllBytes("file.txt");
```

---

##  File Existence Check

```csharp
bool exists = File.Exists("file.txt");
```

---

##  Copy File

```csharp
File.Copy("source.txt", "dest.txt", true); // true = overwrite
```

---

##  Move File

```csharp
File.Move("old.txt", "new.txt");
```

---

##  Delete File

```csharp
File.Delete("file.txt");
```

---

##  Get / Set File Attributes

```csharp
FileAttributes attr = File.GetAttributes("file.txt");
File.SetAttributes("file.txt", FileAttributes.ReadOnly);
```

---

#  Directory Operations (`Directory` Class)

Static methods for folders.

---

##  Create Directory

```csharp
Directory.CreateDirectory("MyFolder");
```

---

##  Delete Directory

```csharp
Directory.Delete("MyFolder", true); // true = recursive
```

---

##  Check if Directory Exists

```csharp
bool exists = Directory.Exists("MyFolder");
```

---

##  Get Files

```csharp
string[] files = Directory.GetFiles("MyFolder");
```

---

##  Get Directories

```csharp
string[] dirs = Directory.GetDirectories("MyFolder");
```

---

##  Move Directory

```csharp
Directory.Move("OldFolder", "NewFolder");
```

---

#  Path Operations (`Path` Class)

Helps manipulate file paths.

---

##  Combine Paths

```csharp
string fullPath = Path.Combine("Folder", "file.txt");
```

---

##  Get File Name

```csharp
string name = Path.GetFileName("C:\\Folder\\file.txt");
```

---

##  Get Extension

```csharp
string ext = Path.GetExtension("file.txt");
```

---

##  Get Directory Name

```csharp
string dir = Path.GetDirectoryName("C:\\Folder\\file.txt");
```

---

 Change Extension

```csharp
string newPath = Path.ChangeExtension("file.txt", ".doc");
```

---

#  FileInfo & DirectoryInfo (Instance-Based Operations)

More detailed control than static classes.

---

##  FileInfo Example

```csharp
FileInfo file = new FileInfo("file.txt");

file.Create();
file.Delete();
file.CopyTo("copy.txt");
file.MoveTo("new.txt");

long size = file.Length;
DateTime created = file.CreationTime;
```

---

##  DirectoryInfo Example

```csharp
DirectoryInfo dir = new DirectoryInfo("MyFolder");

dir.Create();
dir.Delete(true);

FileInfo[] files = dir.GetFiles();
DirectoryInfo[] subDirs = dir.GetDirectories();
```

---

#  Stream Operations

Streams allow low-level IO control.

---

## 🔹 FileStream

Used for reading/writing bytes.

```csharp
FileStream fs = new FileStream("file.txt", FileMode.OpenOrCreate, FileAccess.ReadWrite);

byte[] data = System.Text.Encoding.UTF8.GetBytes("Hello");
fs.Write(data, 0, data.Length);

fs.Close();
```

Common `FileMode`:

- `Create`
    
- `Open`
    
- `Append`
    
- `OpenOrCreate`
    
- `Truncate`
    

Common `FileAccess`:

- `Read`
    
- `Write`
    
- `ReadWrite`
    

---

## 🔹 StreamReader (Read Text)

```csharp
using (StreamReader sr = new StreamReader("file.txt"))
{
    string line = sr.ReadLine();
}
```

---

## 🔹 StreamWriter (Write Text)

```csharp
using (StreamWriter sw = new StreamWriter("file.txt"))
{
    sw.WriteLine("Hello");
}
```

---

## 🔹 BinaryReader

```csharp
using (BinaryReader br = new BinaryReader(File.Open("file.bin", FileMode.Open)))
{
    int number = br.ReadInt32();
}
```

---

## 🔹 BinaryWriter

```csharp
using (BinaryWriter bw = new BinaryWriter(File.Open("file.bin", FileMode.Create)))
{
    bw.Write(123);
}
```

---

## 🔹 MemoryStream (In-memory data)

```csharp
MemoryStream ms = new MemoryStream();
byte[] data = new byte[] { 1, 2, 3 };
ms.Write(data, 0, data.Length);
```

---

## 🔹 BufferedStream (Improves performance)

```csharp
BufferedStream bs = new BufferedStream(new FileStream("file.txt", FileMode.Open));
```

---

#  Drive Operations (`DriveInfo`)

```csharp
DriveInfo drive = new DriveInfo("C");

long freeSpace = drive.AvailableFreeSpace;
long totalSpace = drive.TotalSize;
bool ready = drive.IsReady;
```

---

#  FileSystemWatcher (Monitor Changes)

Monitors file system events.

```csharp
FileSystemWatcher watcher = new FileSystemWatcher();
watcher.Path = "MyFolder";
watcher.Filter = "*.txt";

watcher.Created += (s, e) => Console.WriteLine("File Created");
watcher.EnableRaisingEvents = true;
```

Events:

- `Created`
    
- `Deleted`
    
- `Changed`
    
- `Renamed`
    

---

#  Compression (System.IO.Compression)

Requires:

```csharp
using System.IO.Compression;
```

### Create ZIP

```csharp
ZipFile.CreateFromDirectory("Folder", "archive.zip");
```

### Extract ZIP

```csharp
ZipFile.ExtractToDirectory("archive.zip", "Extracted");
```

---

#  Asynchronous IO

Most IO methods have async versions.

### Example

```csharp
await File.WriteAllTextAsync("file.txt", "Hello");
string content = await File.ReadAllTextAsync("file.txt");
```

---

#  Temporary Files

```csharp
string tempFile = Path.GetTempFileName();
string tempPath = Path.GetTempPath();
```

---

#  Random Access (Seek)

```csharp
FileStream fs = new FileStream("file.txt", FileMode.Open);
fs.Seek(0, SeekOrigin.Begin);
```

---

#  Text Encoding

```csharp
File.WriteAllText("file.txt", "Hello", System.Text.Encoding.UTF8);
```

---

#  Summary of Major Classes in `System.IO`

- `File`
    
- `Directory`
    
- `Path`
    
- `FileInfo`
    
- `DirectoryInfo`
    
- `FileStream`
    
- `StreamReader`
    
- `StreamWriter`
    
- `BinaryReader`
    
- `BinaryWriter`
    
- `MemoryStream`
    
- `BufferedStream`
    
- `DriveInfo`
    
- `FileSystemWatcher`
    

---

# Important Best Practice

Always use `using` for streams:

```csharp
using (FileStream fs = new FileStream("file.txt", FileMode.Open))
{
    // Work with stream
}
```

This ensures proper resource disposal.


## Exception Handling

The main goal of Exception Handling is to catch the exceptions that can arise during the application execution and handle them.

Exception should the handled correctly because in real time application exceptions can crash the application because it make the code to abruptly exit.

Exceptions are raised when CLR is unable to execute a statement.

if we are using "Try" then "Catch" block is mandatory.

"Finally" block and multiple "catch" blocks are optional.

"Try" block contains all the actual code, where exception may occur.
- Multiple "try" blocks for one catch block is not allowed.
- Nested "try" block is allowed.


"Catch" block contains error handling code, it executes only when a particular type of exception is raised during the execution of "try" block.

Multiple "catch" block is allowed/

"Finally" block executes after successful completion of "Try" block, or after any catch block, it is optional.

"throw" keyword is used to throw built in or custom exceptions, in case of invalid values found.


## Format Exception

Format Exception is raised when the CLR cannot convert value from one type to another type due to the format.

lets say changing numbers from string to int.

it cannot change string into int if the string has whitespace or alphabets in this situations format Exception raised.

```
Try{
	//code
}
catch (FormatException){
	//code
}
```


## IndexOutOfRangeException

IndexOutOfRangeException represents an error when an index was supplied outside the available range to an array.

Occurs when accessing an array with a wrong index value, which is less than 0 or greater than or equal to size of the array.

It's a bad practice to throw IndexOutOfRangeException implicitly/explicitly.

## Null reference Exception

Null reference exception represents an error when you try to access a property, indexer or method through a reference variable when its value is null.

it's a bad practice to throw NullReferenceException implicitly/explicitly.

## Argument Null Exception

ArgumentNullException represents an error when a null value is passed as argument to a method, and that method doesn't accept null's into that parameter

it's a good practice to throw ArgumentNullException implicitly / explicitly.

## Inner Exception

Inner Exception is an exception, that is the root cause of another exception.

An exception that is raised due to another exception is called Inner Exception.

## ArgumentOutOfRangeException

It is thrown when a method has received a numeric argument value into a parameter, but it is not in the valid numeric range.

ArgumentOutOfRangeException represents an error when a numeric value is passed as argument to a method, and it outside the acceptable range of values accepted by that methods.

It is a good practice to throw ArgumentOutOfRangeException implicitly / explicitly.


## Argument Exception

Apart from null and range validation all other validation should use Argument Exception 

Argument Exception represents an error when the argument value of a parameter is invalid as per any validation rules / requirements.

it is a good practice to throw ArguementException implicitly / explicitly


## InvalidOperationException

It is thrown when a method call is invalid as per the current state of the object.

## Custom Exception

Custom Exception class is a class that is derived from any one of the exception classes (such as System.Exception or any other exception class.)

If none of the pre defined exception class meets your requirement, you will create an user-defined exception class(custom exception class).


## Catch when or Exception filters

we can write condition to execute the catch block
it is not mostly used


## Top level Statements

You can directly write codes without using class, namespace, or Main method

```
System.Console.WriteLine("Hello, World!");
```

this single statement can return "Hello world".

## File Scoped Namespaces

A new syntax for namespace is introduced

```
namespace name;

class program
{

}
```

the above statement is compiled as 

```
namespace name
{
	class program
	{
	
	}
}
```


## Global Using

to Import a namespace repeatedly "global using" import the namespace into all other files in the current project

lets say there is a namespace called validation

instead of importing it in each file of the project

```
global using namespace_name;
```

By using above statement, that particular namespace will be imported in all the files in the current project.

## module Initializer

Module Initializer is startup logic

This block contains code that should be executed in startup of the application and not run again.

lets say we have to establish a connection to the database the code in module initializer will execute and establish the connection at the starting of the application.

It should be "static" and "void".


## Null reference Types

Nullable reference types and non-nullable reference types allows the compiler to perform "static flow analysis" for purpose of null safety.

By default, all classes and interfaces are 'non nullable reference types'.

To convert them as 'nullable reference type', suffix a question mark (?)

E.g. : class? , variable?


## Null forgiving operator

The compiler can perform a static analysis to identify where there is a possibility of 'null' values and can show warning, so we can avoid null reference exception at coding time itself.


## Targeted-typed 'new' expressions

This allows the developer "not to mention" the class name, but allows to create an object in the 'new' expression

```
class_name variable_name = new(); // equivalent to "new class_name()";
```


# [[Threading]]

Threading a concept that is used for utilizing all the cores of a CPU.
