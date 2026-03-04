CLR is the runtime environment for .Net applications
Microsoft implementations of CLI
Responsible for execution MSIL
CLR is the heart of .NET runtime

The services provided by the CLR are

### 1. Just-In-Time compiler (JIT)

this converts MSIL into native machine code
compiles method by method
improves performance

these are types of JIT
- Normal JIT
- Pre JIT (NGen)
- Tiered JIT

### 2. Garbage Collection (CG)

This is responsible for 
- Automatic memory management
- Frees unused objects
- uses Generational GC
Generations
- Gen0 (short lived objects)
- Gen 1
- gen 2 (long lived objects)

### 3. Memory management
- stack allocation
- heap allocation
- object lifetime tracking
- prevents memory leaks

### 4. Exception Handling
- structured exception handling
- Languages-independent exceptions
- uses try-catch-finally

### 5. Security
- Code Access security (CAS)
- Types safety verification
- prevents unsafe code execution

### 6. Thread Management
 - Manages Threads
 - supports: 
     - Multithreading
     - Async programming
 - Integrates with OS threads


