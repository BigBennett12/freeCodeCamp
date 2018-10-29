---
title: Group-By
---

# Group-By

Group-By is a method used on collections in order to group the elements in such collection by a specific key.

### Signature
```csharp
public static System.Collections.Generic.IEnumerable<TResult> GroupBy<TSource,TKey,TElement,TResult> 
(this System.Collections.Generic.IEnumerable<TSource> source, Func<TSource,TKey> keySelector, Func<TSource,TElement> elementSelector, 
Func<TKey,System.Collections.Generic.IEnumerable<TElement>,TResult> resultSelector);
```

## Example
```csharp
var fruits = new List<Fruit>() {
    new Fruit() { Id = 1, Name = "Orange",     Color = "Orange", Quantity: 3   },
    new Fruit() { Id = 2, Name = "Strawberry", Color = "Red",    Quantity: 12  },
    new Fruit() { Id = 3, Name = "Grape",      Color = "Purple", Quantity: 25  },
    new Fruit() { Id = 4, Name = "Pineapple",  Color = "Yellow", Quantity: 1   },
    new Fruit() { Id = 5, Name = "Apple",      Color = "Red",    Quantity: 5   },
    new Fruit() { Id = 6, Name = "Mango",      Color = "Yellow", Quantity: 2   }
};

// Group Fruit objects by their Color Property, and then count how many fruits are in each group along with the names of each fruit.
var groupFruitByColor = fruits.GroupBy(x => x.Color)
    .Select(t => new {Color = t.Key, Names = t.Select(z => z.Name), Count = t.Count()})
    .ToList();
      
foreach(var item in groupFruitByColor)
{
  Console.WriteLine(item.Color + " - " + item.Count);
  Console.WriteLine("Name of Fruits:");
  
  foreach(var name in item.Names)
  {
    Console.WriteLine(name);	
  }
  Console.WriteLine();
}

```

## Group-By Lambda Explanation

 1. Group By Color
    ```
    fruits.GroupBy(x => x.Color) // (key)
    ```
 2. Use '.Select' to create an anonymous class to get the color, count, and names of fruits
    ```
    .Select(t => new {Color = t.Key, Names = t.Select(z => z.Name), Count = t.Count()})
    ```
  3. Cast to a list object
    ```
    .ToList();
    ```
