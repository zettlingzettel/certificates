## 1/99 PROBLEM

## TASK:
Write a function last that accepts a list and returns the last element in the list.

If the list is empty:

In languages that have a built-in option or result type (like OCaml or Haskell), return an empty option

In languages that do not have an empty option, just return null

## SAMPLE TEST:

describe("last", function(){
  it("should work with non-empty lists", function(){
    Test.assertEquals( last([1,2,3]), 3, "last([1,2,3]) == 3");
  });
  it("should work with empty lists", function(){
    Test.assertEquals( last([]), null, "last( [] ) == null");
  });
});

## SOLUTION:
an alternative to an if...else statement

condition is followed by a question mark (?)
if an expression is truthy the operation is executed
if the condition is falsy the expression followed by a colon (:) is executed 

## 1.
**const last = xs => xs.length ? xs[xs.length - 1] : null**
- if `xs.length ? ` means if `xs` list exists and includes any data 
- `xs[xs.length - 1]` means the name of the list and the index of the last element in the list (indexes start from [0])

## 2.
**const last = xs => xs.length == 0 ? null : xs[xs.length - 1]**


