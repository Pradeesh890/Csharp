## [[LINQ]]

# OOP Features in C# – Quick Notes

## 1. Encapsulation

- **Binding data and methods** together in a single unit (class).
    
- Protects data using **access modifiers** (`private`, `public`, `protected`).
    
- Achieved using **properties, getters, and setters**.
    
- Improves **data security and control**.
    

**Example:**

```csharp
class Person
{
    private string name;   // hidden data

    public string Name     // property
    {
        get { return name; }
        set { name = value; }
    }
}
```

---

## 2. Abstraction

- **Hides internal implementation** and shows only essential details.
    
- Achieved using **abstract classes** and **interfaces**.
    
- Focuses on **what to do**, not **how to do**.
    

**Example:**

```csharp
abstract class Shape
{
    public abstract void Draw();
}

class Circle : Shape
{
    public override void Draw()
    {
        Console.WriteLine("Drawing Circle");
    }
}
```

---

## 3. Inheritance

- Allows a class (**child/derived**) to use properties and methods of another class (**parent/base**).
    
- Promotes **code reuse** and **hierarchical design**.
    
- Uses `:` symbol in C#.
    

**Example:**

```csharp
class Animal
{
    public void Eat()
    {
        Console.WriteLine("Animal eats");
    }
}

class Dog : Animal
{
    public void Bark()
    {
        Console.WriteLine("Dog barks");
    }
}
```

---

## 4. Polymorphism

Means **many forms** — same method behaves differently.

### a) Compile-time Polymorphism (Method Overloading)

- Same method name, **different parameters**.
    
- Decided at **compile time**.
    

```csharp
class MathHelper
{
    public int Add(int a, int b) => a + b;
    public int Add(int a, int b, int c) => a + b + c;
}
```

### b) Runtime Polymorphism (Method Overriding)

- Method in **base class overridden in derived class**.
    
- Uses `virtual` and `override`.
    

```csharp
class Animal
{
    public virtual void Sound()
    {
        Console.WriteLine("Animal sound");
    }
}

class Dog : Animal
{
    public override void Sound()
    {
        Console.WriteLine("Dog barks");
    }
}
```

---

## 5. Association

- **Relationship between two separate classes**.
    
- One object **uses** another object.
    
- Types: **Aggregation** and **Composition**.
    

**Example:**

```csharp
class Engine { }

class Car
{
    private Engine engine = new Engine();
}
```

---

## 6. Aggregation

- **Weak relationship** (“has-a”).
    
- Child object **can exist independently** of parent.
    

```csharp
class Student { }

class College
{
    public Student student;  // independent object
}
```

---

## 7. Composition

- **Strong relationship**.
    
- Child object **cannot exist without parent**.
    

```csharp
class Heart { }

class Human
{
    private Heart heart = new Heart(); // dependent
}
```

---

## 8. Interface

- Contains **only method declarations** (no implementation).
    
- Supports **multiple inheritance** in C#.
    
- Implemented using `:`.
    

```csharp
interface IAnimal
{
    void Sound();
}

class Dog : IAnimal
{
    public void Sound()
    {
        Console.WriteLine("Dog barks");
    }
}
```

---

# Methods in OOP (C#) – Quick Notes

## 1. Instance Method

- Belongs to an **object** of a class.
    
- Requires an **object creation** to call the method.
    
- Can access **instance variables** and **static variables**.
    

**Example:**

```csharp
class Student
{
    public void ShowName()
    {
        Console.WriteLine("Instance Method Called");
    }
}

// Calling
Student s = new Student();
s.ShowName();
```

---

## 2. Static Method

- Belongs to the **class**, not the object.
    
- Called using the **class name**.
    
- Can access **only static members** directly.
    

**Example:**

```csharp
class MathHelper
{
    public static void Display()
    {
        Console.WriteLine("Static Method Called");
    }
}

// Calling
MathHelper.Display();
```

---

## 3. Abstract Method

- Declared in an **abstract class**.
    
- Has **no body** (only declaration).
    
- Must be **implemented in derived class**.
    
- Used to achieve **abstraction**.
    

**Example:**

```csharp
abstract class Animal
{
    public abstract void Sound();
}

class Dog : Animal
{
    public override void Sound()
    {
        Console.WriteLine("Dog barks");
    }
}
```

---

## 4. Virtual Method

- Defined in **base class** with body.
    
- Can be **overridden in derived class** using `override`.
    
- Supports **runtime polymorphism**.
    

**Example:**

```csharp
class Animal
{
    public virtual void Sound()
    {
        Console.WriteLine("Animal sound");
    }
}

class Cat : Animal
{
    public override void Sound()
    {
        Console.WriteLine("Cat meows");
    }
}
```

---

## 5. Sealed Method

- Prevents **further overriding** in derived classes.
    
- Used with `override sealed`.
    

**Example:**

```csharp
class A
{
    public virtual void Show() { }
}

class B : A
{
    public sealed override void Show() { }
}
```

---

## 6. Method Overloading (Compile-time Polymorphism)

- Same **method name**, but **different parameters**  
    (number, type, or order).
    
- Resolved at **compile time**.
    

**Example:**

```csharp
class Calculator
{
    public int Add(int a, int b) => a + b;
    public double Add(double a, double b) => a + b;
}
```

---

## 7. Method Overriding (Runtime Polymorphism)

- Same **method signature** in base and derived class.
    
- Base method must be **virtual/abstract**.
    
- Uses `override`.
    

**Example:**

```csharp
class Bird
{
    public virtual void Fly()
    {
        Console.WriteLine("Bird flies");
    }
}

class Sparrow : Bird
{
    public override void Fly()
    {
        Console.WriteLine("Sparrow flies fast");
    }
}
```

---

## 8. Extension Method

- Adds **new functionality to existing class**  
    **without modifying source code**.
    
- Must be **static method in static class**.
    
- First parameter uses `this`.
    

**Example:**

```csharp
public static class StringHelper
{
    public static int WordCount(this string str)
    {
        return str.Split(' ').Length;
    }
}
```

Usage:

```csharp
string text = "Hello World";
int count = text.WordCount();
```

---
