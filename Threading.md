
## Types of Program Execution 

### Sequential
In this Execution type a single core runs the whole program sequentially.

### Concurrent

In the concurrent program execution Multiple cores split the task and execute each task.

Context switching is when a program switches the processing from one task or another.

Concurrent execution is concept where the programmer can divide the program into independent parts (threads) and can execute them in order independent manner or in partial order, without affecting the outcome.

### Parallel 

In the parallel execution the program runs each task in the each core individually in parallel this reduces the runtime and utilizes all the cores.

Parallel execution is a concept that enables a program to execute multiple tasks simultaneously, typically by utilizing multiple CPUs or processing cores.

### Concurrent & parallel execution

the problem in parallel execution is when a single application takes all the cores in a CPU for running no other programs can run

so concurrent & parallel execution is combination of both concurrent and parallel execution it uses all the cores with context switching

It is a combination of both concurrent execution and parallel execution. The threads may executes in parallel (based on time slicing algorithm of the O/S)

![[Pasted image 20260304104251.png]]


A Thread is a light weight unit of execution within a process.

Multi threading refers to the ability to create and run more than one independent threads concurrently within a single process.

it enables concurrent program execution.

By default, all the code written in the entire C# application executes under a default thread called "Main thread".

The main advantage of threading is improved performance due to the program being run in multiple cores it increases the overall performance of the program.

Multi threading can help to increase the overall performance of a program by allowing it take full utilization of multiple cores of the processor.

It also improves the UI responsiveness of a program by allowing it to executes tasks in background, without making the UI hang / stuck until the task gets fully completed.

By default, all the code written in entire C# application executes under a default thread called "Main Thread".

We have predefined class called thread class to represent a Thread.

as C# is a object oriented language every thread should be treated as a object of predefined class called thread class.

If you want to know the current working thread we a property for thread called 

Each thread object is type of System.threading.Thread

The "System.Threading.Thread" class represents a thread in a application

A thread represents light weight unit of execution that contains its own set of instruction to execute.

### Constructors of thread class

There are two constructors 

1. Thread (ThreadStart ThreadStart)
2. Thread(ParameterizedThreadStart ParameterizedThreadStart)

### Properties of Threads

``` csharp
 1. String Name {get; set;}
 2. ThreadPriority Priority {get; set;}
 3. bool IsActivwe {get;}
 4. boot IsBackground {get; set;}
 5. ThreadState Threadstate {get;}
 6. int ManagedThreadId {get;}
 7. static Thread CurrentThread {get;} 
```

The Name property is used to get the current thread name

The Priority is communicated with the operating system and based on the priority the OS reserves the CPU clock for the particular thread.

If a particular thread has more priority then the OS will allocate more CPU clock to that thread when compared to low priority thread.

Priority represents a value that determines the relative importance of the thread compared to other threads in the system.

Options in "ThreadPriority" enum : Lowest | BelowNormal | Normal | AboveNormal | Highest.

Actual thread execution speed / completion time depends on various factors such as amount of code of the thread, OS's time slicing algorithm etc.

