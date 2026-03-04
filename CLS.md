Common language Specfication
This is subset of CTS
This is not coding thing or something like that 
this is purely Rules that must followed

This defines rules that languages must follow to be interoperable
Not all CTS features are CLS-Compliant

CLS = "minimum rules languages must follow to work together"

## CLS Important Rules
1. No Unsigned Types (uint,ushort) in public APIs
2. Method names must differ by more than case
3. Only one inheritance (no multiple class inheritance)
4. Must support basic types like :
    - Int
    - String
    - Bool

CLS Exists because some languages don't support certain features

So CLS ensures maximum compatibility

for example 
C# support uint
VB.NET does NOT
So uint is not CLS-Compliant