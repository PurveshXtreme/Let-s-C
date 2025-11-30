# 📘 C# Notes for Campus Placements  
Well-structured, beginner-friendly, interview-oriented.

---

# 📑 Table of Contents

### **1. C# Basics**
- [1.1 What is C#?](#what-is-c)
- [1.2 Features of C#](#features-of-c)
- [1.3 CLR, CTS, CLS](#clr-cts-cls)
- [1.4 Data Types](#data-types)
- [1.5 Variables, const, readonly](#variables-const-readonly)
- [1.6 Type Conversions](#type-conversions)
- [1.7 Operators](#operators)
- [1.8 Nullable Types](#nullable-types)

### **2. Interview Questions**
- [2.1 Difference Between C and C#](#difference-between-c-and-c)
- [2.2 What is enum in C#?](#what-is-enum)
- [2.3 What are namespaces?](#what-are-namespaces)
- [2.4 What can namespaces contain?](#namespace-members)

---
- [2. Control Flow & Error Handling](#control-flow)



# -------------------------------------------
# 1. C# Basics
# -------------------------------------------

## <a id="what-is-c"></a> **1.1 What is C#?**

C# (C-Sharp) is a **modern, object-oriented, type-safe programming language** created by **Microsoft** for the **.NET ecosystem**.

### ⭐ Key Points
- Strongly-typed
- Memory-safe (Automatic Garbage Collection)
- Multi-paradigm (OOP + imperative + functional features)
- Rich standard library
- Modern syntax

### ⭐ Used for
- Desktop apps (Windows Forms, WPF)
- Web development (ASP.NET)
- Mobile apps (Xamarin, .NET MAUI)
- Game development (Unity)
- Enterprise applications  
[🔼 Back to TOC](#-table-of-contents)

---

## <a id="features-of-c"></a> **1.2 Features of C#**

- **Object-Oriented**  
- **Type-safe**  
- **Garbage-collected**  
- **Component-oriented**  
- **Interoperable** (works with other .NET languages)  
- **Modern constructs**:  
  Delegates, Events, Generics, LINQ, async/await  

[🔼 Back to TOC](#-table-of-contents)

---

## <a id="clr-cts-cls"></a> **1.3 CLR, CTS, CLS (High-Level)**

### ✔ **CLR — Common Language Runtime**
The runtime environment for .NET applications.  

Handles:
- Memory management  
- Garbage collection  
- JIT compilation  
- Exception handling  
- Thread management  

---

### ✔ **CTS — Common Type System**
Defines how data types behave across .NET languages.

Ensures:
- `int` in C# = `Int32` in IL  
- Compatible types between languages  

---

### ✔ **CLS — Common Language Specification**
A subset of rules that ensure cross-language interoperability.

If code is CLS-compliant → It can be used in VB.NET, F#, etc.  

[🔼 Back to TOC](#-table-of-contents)

---

## <a id="data-types"></a> **1.4 Data Types**

C# data types are divided into:

---

### ✔ **Value Types**  
Stored on **stack**, contain actual data.  
Examples:  
- `int`, `double`, `bool`, `char`  
- `struct`  
- `enum`

Copy-by-value behavior.

---

### ✔ **Reference Types**  
Stored on **heap**, stack only holds reference.  
Examples:  
- `class`  
- `string`  
- `array`  
- `delegate`  
- `interface`

Copy-by-reference behavior.

[🔼 Back to TOC](#-table-of-contents)

---

## <a id="variables-const-readonly"></a> **1.5 Variables, const, readonly**

### ✔ Variables
Value can change any time.

```csharp
int x = 10;
x = 20;
```

---

### ✔ const  
- Assign only once  
- Must be assigned at declaration  
- Compile-time constant  

```csharp
const int A = 10;
```

---

### ✔ readonly  
- Value assigned at declaration **or inside constructor**  
- Runtime constant  

```csharp
readonly int B;

public MyClass() {
    B = 20;
}
```

---

### ⭐ const vs readonly (Interview Favorite)

| Feature | const | readonly |
|--------|--------|-----------|
| Assignment | Only at declaration | Declaration or constructor |
| Time | Compile-time | Runtime |
| Static? | Yes | No (per object) |

[🔼 Back to TOC](#-table-of-contents)

---

## <a id="type-conversions"></a> **1.6 Type Conversions**

### ✔ Implicit (safe)
```csharp
int a = 5;
double b = a;
```

---

### ✔ Explicit (casting)
```csharp
double x = 9.7;
int y = (int)x; // 9
```

---

### ✔ Convert class
```csharp
int n = Convert.ToInt32("123");
```

---

### ✔ Parse
```csharp
int n = int.Parse("123");
```

[🔼 Back to TOC](#-table-of-contents)

---

## <a id="operators"></a> **1.7 Operators**

- **Arithmetic**: + - * / %  
- **Relational**: == != > < >= <=  
- **Logical**: && || !  
- **Assignment**: = += -= *= /=  
- **Increment/Decrement**: ++ --  
- **Ternary**: `? :`  
- **Null-Coalescing**:  
  ```csharp
  x = value ?? defaultValue;
  ```

[🔼 Back to TOC](#-table-of-contents)

---

## <a id="nullable-types"></a> **1.8 Nullable Types**

Value types cannot normally be null:  
`int x = null; // ❌`

---

### ✔ Nullable type:
```csharp
int? x = null;
```

### ✔ Check:
```csharp
if (x.HasValue) Console.WriteLine(x.Value);
```

Used for:
- DB operations  
- Optional fields  
- Missing values  

[🔼 Back to TOC](#-table-of-contents)

---

# -------------------------------------------
# 2. Interview Questions
# -------------------------------------------

## <a id="difference-between-c-and-c"></a> **2.1 Difference Between C and C#**

| Feature | C | C# |
|---------|-----|------|
| Paradigm | Procedural | Object-Oriented |
| Memory | Manual | Garbage Collected |
| Safety | Low-level | Type-safe |
| Platform | OS-dependent | .NET runtime |
| Use cases | OS, Embedded | Web, Mobile, Desktop, Enterprise |

### ⭐ Summary
C is low-level procedural.  
C# is high-level OOP and memory-safe.

[🔼 Back to TOC](#-table-of-contents)

---

## <a id="what-is-enum"></a> **2.2 What is enum in C#?**

Enum = user-defined type with **named constants**.

Example:
```csharp
enum Days { Monday, Tuesday, Wednesday }
```

Characteristics:
- Underlying type = int
- Starts from 0
- Improves readability
- Avoids magic numbers

[🔼 Back to TOC](#-table-of-contents)

---

## <a id="what-are-namespaces"></a> **2.3 What are namespaces?**

A namespace is a **container for organizing code**.

Purpose:
- Avoid name conflicts  
- Group related classes  

Example:
```csharp
namespace MyApp.Utilities
{
    class Helper { }
}
```

[🔼 Back to TOC](#-table-of-contents)

---

## <a id="namespace-members"></a> **2.4 What can namespaces contain?**

Namespaces can contain:
- Classes  
- Interfaces  
- Structs  
- Enums  
- Delegates  
- Other namespaces  

Example:
```csharp
namespace Example 
{
    class A { }
    struct B { }
    enum Colors { Red, Blue }
    interface ITest { }
    delegate void MyDelegate();
    namespace Inner { }
}
```

[🔼 Back to TOC](#-table-of-contents)

---
---


# -------------------------------------------
# 🟦 2. Control Flow & Error Handling (C#)
# -------------------------------------------

Control flow and exception handling are **high-frequency topics in campus interviews**.  
You will use them in almost every coding round.

---

# 📘 2.1 Conditional Statements

## ✔ **if–else**
Used for decision-making based on conditions.

```csharp
if (x > 10)
{
    Console.WriteLine("Greater");
}
else if (x == 10)
{
    Console.WriteLine("Equal");
}
else
{
    Console.WriteLine("Smaller");
}
```

### Key Notes:
- Conditions must return **true/false**.
- Use **else if** to avoid multiple independent IF statements.

---

## ✔ **switch**
Used when there are multiple fixed choices.

```csharp
switch (grade)
{
    case 'A':
        Console.WriteLine("Excellent");
        break;

    case 'B':
        Console.WriteLine("Good");
        break;

    default:
        Console.WriteLine("Invalid");
        break;
}
```

### Key Notes:
- Works with: `int`, `string`, `char`, `enum`.
- `break` is mandatory (otherwise fall-through happens, but C# disallows implicit fall-through for safety).

---

# 📘 2.2 Loops

## ✔ **for loop**
Used when number of iterations is known.

```csharp
for (int i = 0; i < 5; i++)
{
    Console.WriteLine(i);
}
```

---

## ✔ **while loop**
Used when the number of iterations is unknown.

```csharp
while (n > 0)
{
    Console.WriteLine(n);
    n--;
}
```

---

## ✔ **do–while**
Executes at least once.

```csharp
do
{
    Console.WriteLine("Runs at least once");
} 
while (condition);
```

---

## ✔ **foreach loop**  
Used for collections (array, list, dictionary).

```csharp
string[] fruits = { "apple", "banana", "cherry" };

foreach (var f in fruits)
{
    Console.WriteLine(f);
}
```

### Key Notes:
- Read-only iteration  
- Cannot modify the collection directly inside foreach  

---

# 📘 2.3 Jump Statements

## ✔ break
Exits loop or switch.

```csharp
for (int i = 1; i <= 10; i++)
{
    if (i == 5) break;
}
```

---

## ✔ continue
Skips current iteration.

```csharp
for (int i = 1; i <= 5; i++)
{
    if (i == 3) continue;
    Console.WriteLine(i);
}
```

---

## ✔ return  
Exits a method and returns value.

```csharp
int Add(int x, int y)
{
    return x + y;
}
```

---

# -------------------------------------------
# 🟦 2.4 Exception Handling
# -------------------------------------------

Used to **handle runtime errors** and prevent program crashes.

---

## ✔ Basic try-catch-finally

```csharp
try
{
    int x = 10 / 0;
}
catch (Exception ex)
{
    Console.WriteLine(ex.Message);
}
finally
{
    Console.WriteLine("Always executes");
}
```

### Meaning:
- **try** → code that may throw exception  
- **catch** → handles the exception  
- **finally** → always runs (closing files, connections, etc.)

---

# 📘 2.5 Multiple Catch Blocks

```csharp
try
{
    int[] arr = new int[2];
    Console.WriteLine(arr[5]);
}
catch (IndexOutOfRangeException ex)
{
    Console.WriteLine("Invalid index");
}
catch (Exception ex)
{
    Console.WriteLine("General exception");
}
```

### Note:
Catch from **specific → general** (important for interviews).

---

# 📘 2.6 throw vs throw ex (VERY Important)

### ✔ throw
Re-throws original exception *with original call stack*.

```csharp
catch (Exception)
{
    throw;   // preserves stack trace
}
```

### ✔ throw ex
Re-throws exception but **resets the call stack** (not recommended).

```csharp
catch (Exception ex)
{
    throw ex;   // loses original call stack
}
```

### Interview Summary:
- **Use `throw` (preferred)**  
- `throw ex` hides original error location  

---

# 📘 2.7 Custom Exceptions

You can define your own exception class:

```csharp
public class AgeException : Exception
{
    public AgeException(string message) : base(message) {}
}
```

Use it:

```csharp
if (age < 18)
{
    throw new AgeException("Age must be 18 or above");
}
```

### Why create custom exceptions?
- To provide **clearer, domain-specific error messages**
- For business logic validation (e.g., "InsufficientBalanceException")

---

# 📘 2.8 Common Built-in Exceptions (Interview-Favorite)

| Exception | Meaning |
|----------|----------|
| DivideByZeroException | Division by zero |
| NullReferenceException | Object reference missing |
| IndexOutOfRangeException | Array index invalid |
| InvalidCastException | Wrong type casting |
| ArithmeticException | Mathematical errors |
| FormatException | Invalid format (e.g., parsing “abc” to int) |

---

# ✔ Summary (Useful for Revision)

- Use **if-else** for conditional logic  
- Use **switch** for fixed options  
- Choose **foreach** for collections  
- `break`, `continue`, `return` control flow  
- Exception handling = `try + catch + finally`  
- **throw** (preferred) vs **throw ex**  
- Custom exceptions for business rules  

---
---




