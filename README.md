# C# Reference Type Modification Surprise

This repository demonstrates a common pitfall in C# involving reference types.  When you assign one reference type object to another, both variables point to the same memory location. Modifying the object through either variable will affect the other. This is not always intuitive, and can lead to subtle bugs.

**Bug.cs** demonstrates this behavior.  Notice how changing the `MyProperty` value through `instance2` also changes the value in `instance1`.  This is because both variables refer to the same object in memory.

**BugSolution.cs** offers a way to avoid this problem, depending on the desired behavior.  Deep cloning can be used in cases where you want to modify an object without affecting other copies, but this solution is not always applicable for complex objects.