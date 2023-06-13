

<style>
#foo {color: red}
</style>

<p id="foo">foo</p>

<p style="color: blue">bar</p>
# Certificate 1
## Week 1

2023 June 13th (challenge-day-1)
### Hands-On Programming with R - Chapter 2
#### 2.1-2.2
~ ~ ~ ~ ~ ~ ~ ~ ~ ~ ~ ~ ~ ~ ~
Functions:
* ls()
* The colon operator (:) returns every integer between two integers. It is an easy way to create a sequence of numbers.
* a <- 1
[1] 1
~ ~ ~ ~ ~ ~ ~ ~ ~ ~ ~ ~ ~ ~ ~

You can name an object in R almost anything you want, but there are a few rules. First, a name cannot start with a number. Second, a name cannot use some special symbols, like ^, !, $, @, +, -, /, or *:

R is case sensitive

 R does not always follow the rules of matrix multiplication. Instead, R uses element-wise execution.

 R will apply the same operation to each element in the set. So for example, when you run die - 1, R subtracts one from each element of die.

If you give R two vectors of unequal lengths, R will repeat the shorter vector until it is as long as the longer vector, and then do the math

Element-wise operations will ensure that values from one observation or case are only paired with values from the same observation or case.
[ This is where the elements in the same row are multiplied by one another. ]

vector recycling
If the length of the short vector does not divide evenly into the length of the long vector, R will return a warning message.

But don’t think that R has given up on traditional matrix multiplication. You just have to ask for it when you want it. You can do inner multiplication with the %*% operator and outer multiplication with the %o% operator.

#### 2.3
~ ~ ~ ~ ~ ~ ~ ~ ~ ~ ~ ~ ~ ~ ~
Functions:
sample takes two arguments: a vector named x and a number named size. sample will return size elements from the vector.
```R
sample(x = 1:4, size = 2)
## 3 2
```

If you’re not sure which names to use with a function, you can look up the function’s arguments with args. To do this, place the name of the function in the parentheses behind args.
```R
args(round)
## function (x, digits = 0) 
## NULL
```
```R
sample(die, size = 2, replace = TRUE)
## 5 5
## the argument replace = TRUE causes sample to sample with replacement. . Each value has a chance of being selected each time. A sample of size one that is independent of the other values.
```

```R
dice <- sample(die, size = 2, replace = TRUE)
dice
## 2 4

sum(dice)
## 6
```
~ ~ ~ ~ ~ ~ ~ ~ ~ ~ ~ ~ ~ ~ ~
 
The data that you pass into the function is called the function’s argument. 

When you link functions together, R will resolve them from the innermost operation to the outermost. 

You can give a function as many arguments as you like as long as you separate each argument with a comma.

You can pass a new value to an optional argument if you want, and R will use the default value if you do not. 

#### 2.4.1
~ ~ ~ ~ ~ ~ ~ ~ ~ ~ ~ ~ ~ ~ ~
Functions:
```R 
my_function <- function() {
  die <- 1:6
  dice <- sample(die, size = 2, replace = TRUE)
  sum(dice)
}
```

R ignores spaces and line breaks and executes one complete expression at a time.

Giving the bones argument a default value. To do this, set bones equal to a value when you define roll2:

```R
roll2 <- function(bones = 1:6) {
  dice <- sample(bones, size = 2, replace = TRUE)
  sum(dice)
}
```
Now you can supply a new value for bones if you like, and roll2 will use the default if you do not.
~ ~ ~ ~ ~ ~ ~ ~ ~ ~ ~ ~ ~ ~ ~

#### 2.6 Scripts
R will run whichever line of code your cursor is on. If you have a whole section highlighted, R will run the highlighted code. Alternatively, you can run the entire script by clicking the Source button. Don’t like clicking buttons? You can use Control + Return as a shortcut for the Run button. On Macs, that would be Command + Return.

Scripts are multi-line code (console has single-line command line).

CREATING A FUNCTION FROM THE SCRIPT
RStudio comes with a tool that can help you build functions. To use it, highlight the lines of code in your R script that you want to turn into a function. Then click Code > Extract Function in the menu bar. RStudio will ask you for a function name to use and then wrap your code in a function call. It will scan the code for undefined variables and use these as arguments.

