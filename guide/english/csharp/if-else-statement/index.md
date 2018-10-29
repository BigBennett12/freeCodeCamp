---
title: If Else Statement
---

# If Else Statement

The If-Else statement executes a block of code depending on whether your precondition is fullfilled or not.

## Example
```

if(boolean expression)
{
// execute this code block if expression evalutes to true
}
else
{
// always execute this code block when above if expression is false
}


int price = 30;

If (price = 30)
{
  Console.WriteLine("Price is equal to 30.");
}

Else 
{
  Console.WriteLine("Price is not equal to 30.");
}
```

Since we already declared our int Price to be 30, this will be the expected output.

Also, if-else statements can contain multiple conditions/outcomes.  This requires the else-if statement as so:

## Example
```

int price = 30;

If (price == 30)
  Console.WriteLine("Price is equal to 30.");

Else If (price > 30)
  Console.WriteLine("Price is greater than 30.");
  
Else 
  Console.WriteLine("Price is less than 30.");
```

As a clean-code tip.. when writing if-else statements.. if the execution code is only one line then there is no need for curly brackets ('{}'), rather just a tab.

## Output
```
Price is equal to 30.
```
