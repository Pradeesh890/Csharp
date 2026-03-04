All the strings are by default are treated as objects of predefined class called system.string.

Index start at zero by default in string.

both "String" and "string" are same.

string stores a set of characters as char\[]

Max no of characters in the string : 2 billion

string is immutable.

### How string object is created

lets say the string is "Hello world"

```
string x = "Hello world";
```

the string object will be created in the heap and the address will be stored in the stack of the variable 

x will hold the address of the object "Hello world" in the heap.

if two variable has same object value then the CLR will only created new variable not new object in the memory

```
string x = "Hello world";
string y = "Hello world";
```

now in the stack there will two variables 'x' and 'y' but both points at same address in the heap.

CASE CONVERSION
ToUpper()
ToUpperInvariant()
ToLower()
ToLowerInvariant()

TRIMMING & PADDING
Trim()
Trim(params char[])
TrimStart()
TrimStart(params char[])
TrimEnd()
TrimEnd(params char[])
PadLeft(int totalWidth)
PadLeft(int totalWidth, char paddingChar)
PadRight(int totalWidth)
PadRight(int totalWidth, char paddingChar)

SEARCHING
Contains(string value)
Contains(string value, StringComparison comparisonType)
StartsWith(string value)
StartsWith(string value, StringComparison comparisonType)
EndsWith(string value)
EndsWith(string value, StringComparison comparisonType)
IndexOf(string value)
IndexOf(string value, StringComparison comparisonType)
IndexOf(char value)
IndexOfAny(char[])
LastIndexOf(string value)
LastIndexOf(char value)
LastIndexOfAny(char[])

SUBSTRING & EXTRACTION
Substring(int startIndex)
Substring(int startIndex, int length)
Split(char[] separator)
Split(string[] separator, StringSplitOptions options)
Remove(int startIndex)
Remove(int startIndex, int count)
Insert(int startIndex, string value)

REPLACING
Replace(string oldValue, string newValue)
Replace(char oldChar, char newChar)

CONCATENATION & JOINING
Concat(string str0, string str1)
Concat(params string[] values)
Join(string separator, string[] values)
Join(string separator, IEnumerable\<string> values)
+ operator
String interpolation $"{}"

COMPARISON
Equals(string value)
Equals(string value, StringComparison comparisonType)
Compare(string strA, string strB)
Compare(string strA, string strB, StringComparison comparisonType)
CompareTo(string value)
CompareOrdinal(string strA, string strB)

CHECKING & VALIDATION
IsNullOrEmpty(string value)
IsNullOrWhiteSpace(string value)

FORMATTING
Format(string format, params object[] args)
Normalize()
Normalize(NormalizationForm form)

CONVERSION & ACCESS
ToCharArray()
ToCharArray(int startIndex, int length)
ToString()
Length (property)
this[int index] (indexer)

ADVANCED / LESS COMMON
Clone()
Copy(string str) (obsolete)
GetHashCode()
EnumerateRunes()
AsSpan()
AsMemory()

RELATED CLASSES
StringBuilder
StringReader
StringWriter
Regex.Match()
Regex.Replace()
Regex.Split()
Regex.IsMatch()

## String Builder

String is immutable but string Builder is mutable.

The system.Text.StringBuilder is a class that represents an appendable string.

The string values stores in string builder can be modified, without recreating stringbuilder object.

#### Capacity of stringbuilder

The "Capacity" property of string builder represents the number of characters that can b stored in the string builder, as per current memory allocation.

when the programmer tries to store much more number of characters than the capacity, string builder automatically increases the "Capacity" property to its double.

the default value of "Capacity" is 16, the programmer can assign its value via constructor or set accessor of the "Capacity" property.
### Methods of stringbuilder

Stringbuilder() -> It initializes the stringbuilder type of object with the default capacity(16).

StringBuilder(int capacity) -> it initializes the StringBuilder type of object with the specified capacity.

StringBuilder(string value) -> it initializes the StringBuilder type of object with the specified value.

StringBuilder(string value, int capacity) -> it initializes the stringbuilder type of object with the specified value and capacity.

### **Properties of stringbuilder.**

int Length{get;set;}

char \[int index] {get;set;}

int Capacity {get;set;}

int MaxCapacity {get;}


String is used when we would like to make less number of changes to the string, when you perform limited number of concatenation operations, when you want to perform extensive search operations using methods such as indexof(), conatins, startswith, etc. 

StringBuilder is used when you want to perform unknown number of / extensive number of changes to a string. when you perform less number of search operations on strings.

