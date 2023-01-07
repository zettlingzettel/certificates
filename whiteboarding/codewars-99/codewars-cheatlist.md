1.
### IF...ELSE statement alternative

- condition is followed by a question mark (?)
- if an expression is truthy the operation is executed
- if the condition is falsy the expression followed by a colon (:) is executed 

<i> Example: </i>
const last = xs => xs.length ? xs[xs.length - 1] : null

