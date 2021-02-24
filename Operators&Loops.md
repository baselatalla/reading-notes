# Operators and Loops 

## Comparison operators 

Equal (==)	Returns true if the operands are equal.	

Not equal (!=)	Returns true if the operands are not equal.	

Strict equal (===)	Returns true if the operands are equal and of the same type. See also Object.is and sameness in JS.

Strict not equal (!==)	Returns true if the operands are of the same type but not equal, or are of different type.	

Greater than (>)	Returns true if the left operand is greater than the right operand.

Greater than or equal (>=)	Returns true if the left operand is greater than or equal to the right operand.	

Less than (<)	Returns true if the left operand is less than the right operand.	

Less than or equal (<=)	Returns true if the left operand is less than or equal to the right operand.	




## loops

Loops offer a quick and easy way to do something repeatedly Most programs require code that runs over and over until some ending condition occurs. Most programming languages, 
including JavaScript, use loops to provide this capability. JavaScript loops have several forms, but the main looping structures use a looping keyword, a condition, and a block. 
These loops execute the loop's body (the block) for as long as the condition remains truthy. We use the term one iteration to describe executing the loop body once. JavaScript
 also has two other loop mechanisms: array abstractions and recursion. We'll see all of these mechanisms in this chapter.

## while Loops

A while loop uses the while keyword followed by a conditional expression in parentheses and a block. The loop executes the block again and again for as long as the conditional
expression remains truthy. In most programs, that loop should ultimately stop repeating. That means that the block must do something that tells JavaScript when the loop should
stop; that is, it needs to arrange for the conditional expression to become falsy. Otherwise, the loop is an infinite loop that never stops repeating.
 
* example:
 let counter = 1;
  while (counter <= 10) {
  console.log(counter);
  counter = counter + 1;
  
  
  ## for Loops:
for loops have the same purpose as while loops, but they use a condensed syntax that works well when iterating over arrays and other sequences. A for loop combines variable initialization, a loop condition, and the variable increment/decrement expression all on the same line, The sole difference between the two loops is the scope of any variables declared by the initialization clause. In the while statement, the scope includes the code that surrounds the loop; in the for statement, the scope is the for statement and its body.
 example :
 var i;
for (i = 0; i < cars.length; i++) {
  text += cars[i] + "<br>";
}
