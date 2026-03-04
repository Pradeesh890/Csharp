Common Type System defines all data types that are supported by .Net
This ensures type safety across all the languages
this enables cross language data sharing

Eg:
An int in C# = Integer in VB.NET -> Same Underlying type

There are multiple CTS Type Categories
#### Value Types
These are stored on **stack**
this has Fast access
Contains actual data
eg:
int
float
double
bool
struct
enum

#### Reference Types
These are store on Heap
Stack holds the reference
supports inheritance
eg:
class
interface
delegate
array
string
object

## CTS RULES
All types ultimately derive from System.Object
This enables
- Boxing
- Unboxing
- Type Casting
- Enforce Strict type checking
