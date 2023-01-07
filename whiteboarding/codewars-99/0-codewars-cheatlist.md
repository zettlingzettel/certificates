### IF...ELSE alternative

- condition is followed by a question mark (?) 
- if an expression is truthy the operation after `?` is executed
- if the condition is falsy the expression followed by a colon `:` is executed 

<i> Example: </i>
const last = xs => xs.length ? xs[xs.length - 1] : null

### RETURN THE LAST ELEMENT
- pop() <br>
returns the value of the last element of array, shortening the array by deleting the last element in the array.

- xs[xs.length - 1] <br>
`xs.length - 1` -- is the index of the last element