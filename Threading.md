
## Types of Program Execution 

### Sequential
In this Execution type a single core runs the whole program Sequentially.

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

#### IsAlive

Represents a boolean value that indicates whether the thread is currently running (started or not). It becomes true when the start() method called and becomes false when the thread execution is completed.

#### IsBackground

Represents a boolean value that indicates whether the thread is a background thread or not.

True : The thread will not prevent the application from termination when, even when the thread is not completed.

False : The thread will prevent the application from terminating when, even when the thread is not completed.

#### ThreadState {get;}

Returns an enum value that represents the current state of the thread.

Options that are in "ThreadState" enum :

1. Unstarted : Indicates that the thread has been created but has not yet been started. It is the default value of a new thread.
2. Running : Indicates that the thread is currently running and executing the code.
3. WaitSleepJoin : Indicates that the thread is currently in wait, sleep or join state, and is not executing the code.
4. Suspended : Indicates that the thread is suspended by using the "Thread.Suspend()" method. But the suspend() method is deprecated in .Net core.
5. Aborted : Indicates that the thread is aborted (terminated) by using the "Thread.Abort()" method, but the Abort() method is deprecated in .Net core.
6. Stopped : Indicates that the thread execution has been completed.

 Note : There are few methods called Abort(), Suspend() and Resume() in "Thread" class in earlier version of .Net.

 But these methods are obsolete (deprecated) and not recommended to use in real world application, because they can cause thread instability, deadlocks and other synchronization issues etc.

unstarted -> running -> waitsleepjoin | suspend | aborted | stopped


ThreadStart doesn't support sending parameters by default so we have another class called "ParameterizedThreadstart"

we can send objects in the "ParameterizedThreadStart" in which we can send object.

The trick to send more number of arguments is to create a custom class with required parameters and sending the object of that class.

We should avoid using same property for two threads as it may lead to thread synchronization issues.

to prevent this we us "custom threads" where we include the property of the class that is going to be used by the thread.

E.g. 
``` csharp
class NumberUpCounter
{
    public int Count { get; set; }
    public void Countup()
    {
        try
        { 
            for (int i = 1; i <= Count; i++)
            {
                Console.ForegroundColor = ConsoleColor.Green;
                Console.Write($"{i} , ");
                Thread.Sleep(100);
            }
        }
        catch (ThreadInterruptedException ex)
        {
            Console.WriteLine("\nThread Interrupted: " + ex.Message);
        }
    }
}

class Program
{
    static void Main()
    {
        NumberUpCounter nuc = new() { Count = 100};
        ThreadStart Threadst = new ThreadStart(nuc.Countup);
        tdd.Start();
    }
}
```

We don't use shared resource for below reasons.

### Race Condition

A race condition occurs when multiple threads try to update shared data simultaneously, and the final outcome depends on the order in which the threads are executed. The result becomes unpredictable and can lead to data corruption or incorrect computations.

## Data Inconsistency

When multiple threads read and modify shared data without synchronization, it can lead to data inconsistency. One thread may read the data while another is in the process of modifying it, leading to incorrect results or unexpected behavior.

## Deadlock

A deadlock occurs when two or more threads are blocked indefinitely because each thread is waiting for a resource that is held by another thread. This situation results in a standstill, where no thread can proceed, and the program becomes unresponsive.

## Starvation

Starvation happens when a thread is perpetually denied access to a shared resource because other high - priority threads consistently acquire the resource first. The starved thread cannot make progress and may result in reduced performance.

# Thread Synchronization

Thread synchronization is the process of coordinating the execution of multiple threads to ensure that they do not interfere with each other while accessing shared resources.

This is essential if two or more threads are accessing a shared resource such as a variable / property or any other external resource.

### Thread synchronization mechanisms

1. Monitor
2. Locks
3. Mutex
4. Semaphores

## Monitor

If two threads are accessing the same shared resource and do some operation on that resource only one should be given access at one time after completing one threads operations other thread should get the access until that other thread should be in the waiting state.

By using the monitor class we can do the perform the above operation. 