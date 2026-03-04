Collections are the standard way to store and manipulate group of elements (primitive values or objects).

collections are internally objects of specific "collection classes" such as list, dictionary, sortedlist etc..

E.g. list collection

```
List<type> referenceVariable = new List<type>();
```

Collection can store unlimited elements
we can add, remove elements at any time.
we need not to specify the size (no of elements) while creating collection
you can search, sort, copy collections using various built in methods.
we go for collection for better working without any restriction.

### List collection

List collection contains a group of elements of same type

Full Path : System.Collections.Generic.List

The "list" class is a generic class, so we need to specify the data type of value while creating object.

```
List<type> referenceVariable = new List<type>();
```


- It is dynamically sized. You can add, remove elements at any time.
- It allows duplicate values.
- It is index based. You need to access elements by using zero base index.
- It is not sorted by default. The elements are stored in the same order, how they are initialized.
- It uses arrays internally, that means, recreates array when the elements is add/removed.
- The capacity property holds the number of elements that can be stored in the internal array of the list. if you add more elements, the internal array will resized to the count of elements.

list have some methods
- Add(T)
- AddRange()
- Insert(index, val)
- InsertRange(index, list)
- Remove(value)
- RemoveAt(index)
- RemoveRange(startindex, no of elements to be removed)
- RemoveAll()
- clear()
- IndexOf(value)
- BinarySearch()
- Contains()
- Sort()
- Reverse()
- ToArray()
- ForEach()
- Exists()
- Find()
- FindIndex()
- FindLast()
- FindLastIndex()
- FindAll()
- ConvertAll

### Dictionary

Dictionary collection contains a group of elements of key / value pairs.

The "dictionary" class is a generic class, so you need to specify data type of the key and data type of the value while creating object.

you can set / get the value based on the key.

The key can't be null or duplicate.

```
Dictionary<KeyDataType,ValueDataType> reference = new Dictionary<KeyDataType,ValueDataType>();
```

it is dynamically sized, we can add, remove elements (key/value pairs) at any time.

key can't be null or duplicate, but the value can be null or duplicate

### Sorted List

Sorted List collection contains a group of elements of key/value pairs.

System.Collections.Generic.Sortedlist

In the case of Dictionary it will require a large amount of time to search for a particular key but for a SortedList everything will be automatically sorted while storing.
so for storing millions of data Sorted List is better than Dictionary.

Sorted list is also a generic class, so we need to specify data type of the key and data type of the value while creating object.

Sorted list simply do ascending order sorting based on the keys.

```
SortedList <DataType,DataType> ReferenceVariableName = new SortedList<DataType,DataType>();
```

### HashTable

HashTable collection contains a group of elements of key/value pairs stored at respective indexes.

Hash Table is not a generic type so there is no need for explicit data type mentioning.

Hash table randomly calculates the index and stores the particular key values pairs as linked list at the particular index.

**Process of adding an element:**
1. Generate index based on the key. Ex: index = hash code % size of dictionary.
2. Add the element (key and value) next to the linked list at the generated index.

In the case of key being string, the two string method of string class automatically generates random hash code based on the characters.

In the case of key being a object of a particular class it the developers responsibility to write the get hash code method of system.object.class and get the hash code.

In the case of hash code being same a linked list will be created in the same hash area.

The default size of hash table is 17 by default that is a prime number, if there is more than that value it will increase the size as prime numbers.

The goal of the hash table is searching time.
it should be very much faster than performing linear search in case of dictionary.

but for hundreds or thousands of data the difference is negligible.

The keys should be unique and not null.



### Hashset
hashset collection contains a group of elements of unique values stored at respective indexes.

full path is System.Collections.Generic.Hashset

But in the hashset the index will be calculated based on the hash code of the values instead of key.

But in this case the values must be unique and duplicate values are not allowed.

Process of adding an element:
1. Generate index based on the value. E.g. Index=hashcode % count.
2. Add the element next to the linked list at the generate index.

in the case of numerical values the same value is treated as hash code


### Array List

Array list collection contains a group of elements of any type.

Array list class is not a generic class, so we need not to specify data type value while creating objects.

since it is not a generic class it is present under namespace "system.collections". <- import this to work with array list.

## Stack

Stack collection contains a group of elements based on LIFO (last in first out) operation.

Adding is called as -> push
Removing is called as -> pop

push uses -> top pointer
pop uses -> top pointer

we can only manipulate the elements using peek(), push() and pop().

It is used when we want access the lastly added element first.

## Queue

Queue collection contains a group of elements based on FIFO(first in first out) based collection.

it is also a generic class.
It is used when we want to read the firstly added data at first.

Queue has two ends front and rear.

Adding elements -> enqueue
Removing element -> Dequeue

enqueue at back and dequeue at back.

## Collection of Objects

"Collection of Objects" is an collection object, where each element stores a reference to some other object.

This is used to store details of groups of objects.

## Object Relation
Whenever a field of one class stores the object reference of another class then it is called as object relation.


## Collection Hierarchy

Every predefined collection classes such as list, array, list, stack, queue are implementing a predefined interface.
in other words there are some predefined parents before based on which the collection classes are inherited

At the top of the Hierarchy we two interfaces

IEnumerator t and IEnumerator

the difference is IEnumerator t  is a generic interface so we can only specify one data type for this.

the second one is not a generic interface.

apart from these two we have another two interfaces called 

IEnumerable t  and IEnumerable

first is generic and the second is not generic

Generally all the generic collection classes such as stack, queue, list, etc. are inherited from IEnumerable T 
which is a generic interface.

While coming to IEnumerable we don't specify and data types while creating reference variable or object.

## IEnumerable

The IEnumerable interface represents a groups of elements
It is the parent interface of all types of collections

Every collection class is derived from the IEnumerable interface 

if some class have to use foreach loop it should implement IEnumerator
this gives a Enumerator object that implements IEnumerator T

#### IComparable

The main use case why we use IComparable is for sorting. we can use sort method for sorting but we use comparable because sort method can sort the literal values, but it can't sort the custom objects in out custom collection or custom classes.

this -> holds the last object and
other -> holds the current object.

IComparer

if the developer of base class creates the class without implementing IComparable, how can we sort the objects inside the class so we need to use the IComparer.
IComparer can be implemented a separate class so we can implement the sort in objects without the implementation in original class itself.

the internal mechanism of both IComparer and IComparable is same but the difference is IComparable should be initialized in the class that is created and IComparer can be created as separate class.

