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

---

- [4. Important C# Features (Placement Targeted)](#4-important-c-features-placement-targeted)
  - [4.1 ref vs out](#41-ref-vs-out)
  - [4.2 params Keyword](#42-params-keyword)
  - [4.3 Enums](#43-enums)
  - [4.4 Structs](#44-structs)
  - [4.5 Properties (getset)](#45-properties-getset)
  - [4.6 Indexers](#46-indexers)
  - [4.7 Anonymous Types](#47-anonymous-types)
  - [4.8 var vs dynamic vs object](#48-var-vs-dynamic-vs-object)
  - [4.9 Nullable Types](#49-nullable-types)
  - [4.10 Boxing & Unboxing](#410-boxing--unboxing)
 
---

1. [Difference between `ref` and `out`](#1-difference-between-ref-and-out)
2. [What are Properties in C#?](#2-what-are-properties-in-c)
3. [Difference between `is` and `as` operators](#3-difference-between-is-and-as-operators)
4. [What are Extension Methods?](#4-what-are-extension-methods-in-c)
5. [Ways to Overload a Method](#5-different-ways-to-overload-a-method-in-c)
6. [Accessibility Modifiers](#6-accessibility-modifiers-in-c)

---

# 🟦 5. Collections + Generics (High Priority)

1. [Arrays](#1-arrays)
2. [List\<T\>](#2-listt)
3. [Dictionary\<TKey-TValue\>](#3-dictionarytkey-tvalue)
4. [HashSet\<T\>](#4-hashsett)
5. [Stack\<T\> and Queue\<T\>](#5-stackt-and-queuet)
6. [Advantages of Generics](#6-advantages-of-generics)
7. [IEnumerable vs ICollection](#7-ienumerable-vs-icollection)

---

# 📘 Data Structures & Collections — C# Interview Notes

1. [What is Jagged Array?](#1-what-is-jagged-array)
2. [Array.CopyTo() vs Array.Clone()](#2-arraycopyto-vs-arrayclone)
3. [What is a Tuple in C#?](#3-what-is-a-tuple-in-c)
4. [What are Indexers in C#?](#4-what-are-indexers-in-c)
5. [What is Hashtable in C#?](#5-what-is-hashtable-in-c)
6. [SortedList vs SortedDictionary](#6-sortedlist-vs-sorteddictionary)
7. [Difference between Array and ArrayList](#7-difference-between-array-and-arraylist)




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

# 🟦 4. Important C# Features (Placement Targeted)

Below are the most important C# features frequently asked in campus interviews along with definitions, examples, and key differences.

---

## **4.1 ref vs out**

### **ref**
- Used to pass a variable **by reference**.
- The variable **must be initialized** before passing.
- Both caller and callee must use the `ref` keyword.

#### Example:
```csharp
void Modify(ref int x)
{
    x = x + 10;
}

int num = 5;
Modify(ref num);   // num becomes 15
```

### **out**
- Also passes data by reference.
- The variable **does NOT need to be initialized** before passing.
- The called method **must assign a value** to it.

#### Example:
```csharp
void GetValues(out int x)
{
    x = 50;
}

int num;
GetValues(out num);   // num becomes 50
```

### **ref vs out (Interview Table)**

| Feature | ref | out |
|---------|------|------|
| Initialization required | Yes | No |
| Must assign inside method | No | Yes |
| Usage | When reading + writing | When only writing/output |

---

## **4.2 params Keyword**

Allows a method to accept **variable number of arguments**.

```csharp
int Sum(params int[] nums)
{
    int s = 0;
    foreach (int n in nums) s += n;
    return s;
}

int result = Sum(1, 2, 3, 4);
```

Rules:
- Only **one** params allowed.
- Must be the **last parameter**.

---

## **4.3 Enums**

Used to define a group of named constants.

```csharp
enum Days { Monday, Tuesday, Wednesday, Thursday }
```

- Underlying type is `int` by default.
- Values start from **0, 1, 2...**

---

## **4.4 Structs**

A **value type** used for small, lightweight objects.

```csharp
struct Point
{
    public int X;
    public int Y;
}
```

### Features:
- Stored on **stack**
- Cannot have a default constructor
- Cannot inherit from another class
- Can implement interfaces
- Faster than classes

### Struct vs Class

| Feature | Struct | Class |
|---------|---------|--------|
| Type | Value Type | Reference Type |
| Memory | Stack | Heap |
| Inheritance | No | Yes |
| Performance | Faster | Slower |

---

## **4.5 Properties (get/set)**

Used to encapsulate fields with controlled access.

```csharp
class Person
{
    public string Name { get; set; } // auto-property
}
```

With custom logic:

```csharp
private int age;
public int Age
{
    get => age;
    set => age = (value > 0) ? value : 0;
}
```

---

## **4.6 Indexers**

Allows an object to be accessed like an array.

```csharp
class MyList
{
    private string[] data = new string[5];

    public string this[int index]
    {
        get => data[index];
        set => data[index] = value;
    }
}
```

Usage:
```csharp
MyList list = new MyList();
list[0] = "Hello";
```

---

## **4.7 Anonymous Types**

Used when creating objects **without defining a class**.

```csharp
var emp = new { Name = "Ravi", Age = 22 };
Console.WriteLine(emp.Name);
```

- Read-only properties  
- Mostly used in LINQ

---

## **4.8 var vs dynamic vs object**

### **var**
- Compile-time type inferred by compiler.
- Type cannot change once assigned.

```csharp
var x = 10;    // int
var y = "Hi";  // string
```

---

### **dynamic**
- Type checking happens at **runtime**.
- Can change type anytime.

```csharp
dynamic d = 10;
d = "Hello";   // allowed
```

---

### **object**
- Base type of all .NET types.
- Requires **boxing/unboxing** for value types.

```csharp
object o = 10; // boxed
int x = (int)o; // unboxed
```

---

### Comparison Table

| Feature | var | dynamic | object |
|---------|--------|-----------|---------|
| Bind Time | Compile-time | Run-time | Run-time |
| Type Safety | Yes | No | Yes (but requires casting) |
| Performance | Fast | Slow | Medium |
| Changing Type | No | Yes | Yes (with cast) |

---

## **4.9 Nullable Types**

Allows value types to store **null**.

```csharp
int? x = null;
```

### Checking:
```csharp
if (x.HasValue)
    Console.WriteLine(x.Value);
```

### Null Coalescing Operator:
```csharp
int result = x ?? 100; // if x is null => 100
```

---

## **4.10 Boxing & Unboxing**

### **Boxing**
Converting **value type → object**

```csharp
int x = 10;
object obj = x;   // boxing
```

### **Unboxing**
Converting **object → value type**

```csharp
int y = (int)obj;  // unboxing
```

### Notes:
- Boxing creates **heap allocation**
- Unboxing requires **explicit cast**
- Frequently asked in interviews

---
---

## **1. Difference between `ref` and `out`**
| Feature | `ref` | `out` |
|--------|-------|--------|
| Initialization | Must be initialized before passing | No need to initialize before passing |
| Purpose | Read + Write | Only Write (method must assign value) |
| Direction | Two-way | One-way (returns value through parameter) |
| Use Case | Modify existing value | Return multiple values |

### Example
```csharp
void Add(ref int x)
{
    x += 10;
}

void GetValue(out int y)
{
    y = 100; // must assign
}
```

---

## **2. What are Properties in C#?**
Properties are **class members** that provide **controlled access** to private fields using `get` and `set`.

### Key Points
- Used for **encapsulation**
- `get` → returns value  
- `set` → assigns value  
- Uses implicit `value` keyword  
- Can be **auto-implemented**
- Can be **read-only** or **write-only**

### Example
```csharp
class Student
{
    public int Age { get; set; } // auto property
}
```

---

## **3. Difference between `is` and `as` operators**
### **`is` operator**
- Checks **type compatibility**
- Returns **true/false**

```csharp
if(obj is string) { }
```

### **`as` operator**
- Performs **safe casting**
- Returns object if successful, otherwise **null**
- Does NOT throw exception

```csharp
string s = obj as string;
```

---

## **4. What are Extension Methods in C#?**
Extension methods allow you to **add new methods** to existing classes **without modifying** their source code.

### Requirements
- Must be inside a **static class**
- Must be a **static method**
- First parameter must use **`this` keyword**

### Example
```csharp
public static class MyExtensions
{
    public static int WordCount(this string str)
    {
        return str.Split(' ').Length;
    }
}

int count = "Hello World".WordCount();
```

---

## **5. Different ways to Overload a Method in C#**
A method can be overloaded by changing:

1. Number of parameters  
2. Type of parameters  
3. Order of parameters  

### Example
```csharp
void Show(int x) { }
void Show(double x) { }
void Show(int x, int y) { }
```

---

## **6. Accessibility Modifiers in C#**
| Modifier | Meaning |
|---------|---------|
| **public** | Accessible everywhere |
| **private** | Accessible only within the class |
| **protected** | Accessible in class + derived classes |
| **internal** | Accessible within same assembly |
| **protected internal** | protected + internal |
| **private protected** | Only derived classes **within same assembly** |

---
---

# 🟦 5. Collections + Generics (High Priority)


---

## **1. Arrays**
- Fixed size  
- Fast indexing  
- Stores elements of same type  
- Located in contiguous memory  

### Example
```csharp
int[] arr = new int[3] { 10, 20, 30 };
```

---

## **2. List\<T\>**
- Dynamic array  
- Most commonly used collection  
- Supports Add, Remove, Contains, Sort, etc.

### Example
```csharp
List<int> nums = new List<int>();
nums.Add(10);
nums.Add(20);
```

---

## **3. Dictionary\<TKey, TValue\>**
- Stores **key–value** pairs  
- Fast lookup (O(1) average)  
- Key must be **unique**

### Example
```csharp
Dictionary<int, string> students = new Dictionary<int, string>();
students[1] = "Purvesh";
students[2] = "John";
```

---

## **4. HashSet\<T\>**
- Stores **unique** values only  
- No duplicates allowed  
- No indexing (unordered)  
- Internally uses **hashing**

### Example
```csharp
HashSet<int> set = new HashSet<int>() { 1, 2, 2, 3 };
```
Result → {1, 2, 3}

---

## **5. Stack\<T\> and Queue\<T\>**

### **Stack\<T\> (LIFO – Last In First Out)**
```csharp
Stack<int> st = new Stack<int>();
st.Push(10);
st.Push(20);
int x = st.Pop(); // 20
```

### **Queue\<T\> (FIFO – First In First Out)**
```csharp
Queue<int> q = new Queue<int>();
q.Enqueue(10);
q.Enqueue(20);
int x = q.Dequeue(); // 10
```

---

## **6. Advantages of Generics**
- **Type safety** (no boxing/unboxing)  
- Better **performance**  
- Reusability of code  
- Compile-time error checking  
- Stronger type constraints (`where T : class`, etc.)

### Example
```csharp
List<string> names = new List<string>();
```

---

## **7. IEnumerable vs ICollection**

### **IEnumerable**
- Read-only iteration  
- Can use `foreach`  
- No Add/Remove  
- Suitable for data streams, LINQ  

### **ICollection**
- Inherits from `IEnumerable`  
- Supports Add, Remove, Count  
- Represents an in-memory modifiable collection  

### Summary Table

| Feature | IEnumerable | ICollection |
|--------|-------------|-------------|
| Add/Remove | ❌ No | ✅ Yes |
| Count | ❌ No | ✅ Yes |
| Modify Collection | ❌ No | ✅ Yes |
| Looping | Yes | Yes |
| Use Case | Read-only iteration | Managing collections |

---
---


# 📘 Data Structures & Collections — C# Interview Notes

---

## **1. What is Jagged Array?**
A **Jagged Array** is an array of **arrays**, where each inner array can have **different lengths**.

### Key Points
- Also called **“array of arrays”**
- Stored as **multiple separate arrays**
- Each row can have **different size**
- Useful when data is irregular (e.g., marks of students)

### Example
```csharp
int[][] jagged = new int[3][];
jagged[0] = new int[] { 1, 2 };
jagged[1] = new int[] { 3, 4, 5 };
jagged[2] = new int[] { 6 };
```

---

## **2. Array.CopyTo() vs Array.Clone()**

### **Array.CopyTo()**
- Copies elements into **an existing array**
- Requires the **target array to be already created**
- Performs **shallow copy**

```csharp
int[] a = {1, 2, 3};
int[] b = new int[3];
a.CopyTo(b, 0);
```

### **Array.Clone()**
- Creates a **new array**  
- Returns an **object** → must cast back  
- Also **shallow copy**

```csharp
int[] a = {1, 2, 3};
int[] b = (int[])a.Clone();
```

### Summary

| Feature | CopyTo() | Clone() |
|--------|----------|---------|
| Creates new array | ❌ No | ✅ Yes |
| Needs destination | ✅ Yes | ❌ No |
| Copy type | Shallow | Shallow |

---

## **3. What is Tuple in C#?**
A **Tuple** is a lightweight data structure that holds **multiple values** of different types without creating a class.

### Key Points
- Immutable  
- Can store **multiple types**  
- Useful for returning multiple values  

### Example
```csharp
var person = Tuple.Create("Purvesh", 21, "Pune");
var name = person.Item1;
```

### Modern C# Tuples (ValueTuple)
```csharp
(string name, int age) data = ("Purvesh", 21);
Console.WriteLine(data.name);
```

---

## **4. What are Indexers in C#?**
Indexers allow objects to be accessed **like arrays** using the `[]` operator.

### Key Points
- Provide array-like access to class objects  
- Use `this` keyword  
- Used in collections, custom containers  

### Example
```csharp
class Sample
{
    private int[] arr = new int[5];

    public int this[int index]
    {
        get { return arr[index]; }
        set { arr[index] = value; }
    }
}
```

---

## **5. What is Hashtable in C#?**
`Hashtable` is a **non-generic** collection that stores **key–value pairs** using hashing.

### Key Points
- Keys must be **unique**
- Stores **object** type → **boxing/unboxing**
- Slower compared to `Dictionary<TKey, TValue>`  
- Found in `System.Collections`

### Example
```csharp
Hashtable ht = new Hashtable();
ht["id"] = 101;
ht["name"] = "Purvesh";
```

---

## **6. Difference between SortedList and SortedDictionary**

| Feature | SortedList | SortedDictionary |
|---------|-------------|------------------|
| Internal storage | Array | Red-Black Tree |
| Lookup performance | Faster for index-based access | Faster insert/delete |
| Memory usage | Lower | Higher |
| Order | Sorted by key | Sorted by key |
| When to use | Small collections | Large dynamic collections |

### Summary
- **SortedList** → Better for small, read-heavy collections  
- **SortedDictionary** → Better for frequent insertions & deletions  

---

## **7. Difference between Array and ArrayList**

| Feature | Array | ArrayList |
|---------|--------|-----------|
| Type | Fixed type | Stores `object` (non-generic) |
| Size | Fixed | Dynamic |
| Performance | Faster | Slower (boxing/unboxing) |
| Generic | Yes | No |
| Best for | Known size & type | Unknown size & mixed data (not recommended now) |

### Example
```csharp
int[] arr = new int[3];
ArrayList list = new ArrayList();
list.Add(10);       // boxing
list.Add("text");   // stores object
```

### Modern Replacement  
Use **List<T>** instead of `ArrayList`.

---
---

