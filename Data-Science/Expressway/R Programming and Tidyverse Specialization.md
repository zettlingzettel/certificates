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


2023 June 14th (challenge-day-2)
### R for Data Science - Chapter 4
#### 4.1
Alt + - (the minus sign).
Object names must start with a letter, and can only contain letters, numbers, _ and .


```R
seq(1, 10)
```
surrounding the assignment with parentheses, which causes assignment and “print to screen” to happen.

Alt + Shift + K

2023 June 15th-16th (challenge-day-3-4)
### Fundamentals of R Summary
Objects can be created with the assign operator, <-, and named using letters, digits, dots, and underscores. Note that a name must start with a letter and is case sensitive. 

Objects have two intrinsic properties: mode and length. The mode represents the element type: numeric, character, complex, and logical. The length is the number of elements in the object.

Vector, Matrix, Array, List, Dataframe

```R
x <- 10             # numeric vector 
mode(x)

y <- "my vector"    ### character vector
mode(y)

z <- 10i            ### complex vector
mode(z)

j <- TRUE           ### logical vector
mode(j)
```

```R
dim(data) 
### The dim function of the R programming language returns the dimension (e.g. the number of columns and rows) of a matrix, array or data frame.
```

```R
The mode is the value that has highest number of occurrences in a set of data. Unike mean and median, mode can have both numeric and character data. R does not have a standard in-built function to calculate mode.


If the mode() function in R gives a result of numeric, it means that the vector or matrix has no mode. This can happen if the vector or matrix has all unique values, or if the values in the vector or matrix are evenly distributed.
```

```R
%%
Modulus
% / %
Integer Division
```

```R
Functions:
Description
?() or help()
Access the documentation and help file for a particular function
install.packages()
Download and install an R package
library()
Loads an R package into the working environment
setwd()
Set the working directory
getwd()
Get the working directory
c()
Create a vector
as.numeric()
Converts an object to a numeric vector
as.logical()
Converts an object to a logical vector
as.character()
Converts and object to a character vector
sum()
Returns the sum of all input values
length()
Returns the lenght of the obejct
mean()
Returns the arithmetic mean of the vector
median()
Returns the median of the vector
sample()
Returns a specificed size of elements from the object
replicate()
Repeats an expression a specific number of times
hist()
Creates a histogram of given data values
```

2023 June 14th (challenge-day-5)

Document Everything

Start with the question and the raw data
All files are text files

Platform independence
Future-proof
Make code reachable

Comments
Formatting (indentation)
Meaningful names
Each script does one task


R Markdown Cheat Sheet: Help > Cheatsheets > R Markdown Cheat Sheet,
R Markdown Reference Guide: Help > Cheatsheets > R Markdown Reference Guide.

This is an R Markdown file, a plain text file that has the extension .Rmd:

---
title: "Diamond sizes"
date: 2016-08-25
output: html_document
---

```{r setup, include = FALSE}
library(ggplot2)
library(dplyr)

smaller <- diamonds %>% 
  filter(carat <= 2.5)
```

We have data about `r nrow(diamonds)` diamonds. Only 
`r nrow(diamonds) - nrow(smaller)` are larger than
2.5 carats. The distribution of the remainder is shown
below:

```{r, echo = FALSE}
smaller %>% 
  ggplot(aes(carat)) + 
  geom_freqpoly(binwidth = 0.01)
```


INCLUDES:
An (optional) YAML header surrounded by ---s.
Chunks of R code surrounded by ```.
Text mixed with simple text formatting like # heading and _italics_.

You can run each code chunk by clicking the Run icon (it looks like a play button at the top of the chunk), or by pressing Cmd/Ctrl + Shift + Enter. RStudio executes the code and displays the results inline with the code:


To produce a complete report containing all text, code, and results, click “Knit” or press Cmd/Ctrl + Shift + K. You can also do this programmatically with rmarkdown::render("1-example.Rmd"). This will display the report in the viewer pane, and create a self-contained HTML file that you can share with others.

When you knit the document, R Markdown sends the .Rmd file to knitr, http://yihui.name/knitr/, which executes all of the code chunks and creates a new markdown (.md) document which includes the code and its output. The markdown file generated by knitr is then processed by pandoc, http://pandoc.org/, which is responsible for creating the finished file. The advantage of this two step workflow is that you can create a very wide range of output formats, as you’ll learn about in R markdown formats.

Text formatting 
------------------------------------------------------------

*italic*  or _italic_
**bold**   __bold__
`code`
superscript^2^ and subscript~2~

Headings
------------------------------------------------------------

# 1st Level Header

## 2nd Level Header

### 3rd Level Header

Lists
------------------------------------------------------------

*   Bulleted list item 1

*   Item 2

    * Item 2a

    * Item 2b

1.  Numbered list item 1

1.  Item 2. The numbers are incremented automatically in the output.

Links and images
------------------------------------------------------------

<http://example.com>

[linked phrase](http://example.com)

![optional caption text](path/to/img.png)

Tables 
------------------------------------------------------------

First Header  | Second Header
------------- | -------------
Content Cell  | Content Cell
Content Cell  | Content Cell


 Help > Markdown Quick Reference.


The word "footnote"[^footnote] is a reference to a note at the bottom of the page.

This is a horizontal rule.
---

A horizontal rule in R is a line that is displayed across the entire width of the page. It is used to separate sections of text or to add visual interest to a document.


<style>
hr {
  border: 1px solid red;
}
</style>
This is a horizontal rule.
---

The horizontal rule will now be displayed with a red border.

> This is a block quote.
>
> It can contain multiple paragraphs.


2023 June 25th (challenge-day-3)

27.4 Code chunks

To run code inside an R Markdown document, you need to insert a chunk. There are three ways to do so:

The keyboard shortcut Cmd/Ctrl + Alt + I

The “Insert” button icon in the editor toolbar.

By manually typing the chunk delimiters ```{r} and ```.

You can continue to run the code using the keyboard shortcut that by now (I hope!) you know and love: Cmd/Ctrl + Enter. However, chunks get a new keyboard shortcut: Cmd/Ctrl + Shift + Enter, which runs all the code in the chunk. Think of a chunk like a function. A chunk should be relatively self-contained, and focussed around a single task.

The following sections describe the chunk header which consists of ```{r, followed by an optional chunk name, followed by comma separated options, followed by }. Next comes your R code and the chunk end is indicated by a final ```.

```{r by-name}
```


2023 July 4th (challenge-day-4(4/176))

Chunks can be given an optional name: ```{r by-name}.

You can more easily navigate to specific chunks using the drop-down code navigator in the bottom-left of the script editor:

There is one chunk name that imbues special behaviour: setup. When you’re in a notebook mode, the chunk named setup will be run automatically once, before any other code is run.

http://yihui.name/knitr/options/

eval = FALSE prevents code from being evaluated

include = FALSE runs the code, but doesn’t show the code or results in the final document

echo = FALSE prevents code, but not the results from appearing in the finished file. Use this when writing reports aimed at people who don’t want to see the underlying R code.

message = FALSE or warning = FALSE prevents messages or warnings from appearing in the finished file.

results = 'hide' hides printed output; fig.show = 'hide' hides plots.

error = TRUE causes the render to continue even if code returns an error. This is rarely something you’ll want to include in the final version of your report, but can be very useful if you need to debug exactly what is going on inside your .Rmd. It’s also useful if you’re teaching R and want to deliberately include an error. The default, error = FALSE causes knitting to fail if there is a single error in the document.

If you prefer that data be displayed with additional formatting you can use the knitr::kable function. The code below generates Table 27.1.

knitr::kable(
  mtcars[1:5, ], 
  caption = "A knitr kable."
)

 The solution is cache = TRUE. When set, this will save the output of the chunk to a specially named file on disk. On subsequent runs, knitr will check to see if the code has changed, and if it hasn’t, it will reuse the cached results.

 The caching system must be used with care, because by default it is based on the code only, not its dependencies.

 You can avoid that problem with the dependson chunk option.

 ```{r processed_data, cache = TRUE, dependson = "raw_data"}
processed_data <- rawdata %>% 
  filter(!is.na(import_var)) %>% 
  mutate(new_variable = complicated_transformation(x, y, z))
```


knitr caching only tracks changes within the .Rmd file and not csv

file.info(): it returns a bunch of information about the file including when it was last modified. Then you can write:

```{r raw_data, cache.extra = file.info("a_very_large_file.csv")}
rawdata <- readr::read_csv("a_very_large_file.csv")
```
As your caching strategies get progressively more complicated, it’s a good idea to regularly clear out all your caches with knitr::clean_cache().

27.4.5.
eg 
knitr::opts_chunk$set(
  comment = "#>",
  collapse = TRUE
)

27.4.6 Inline code
We have data about `r nrow(diamonds)` diamonds. Only `r nrow(diamonds) - nrow(smaller)` are larger than 2.5 carats. The distribution of the remainder is shown below:
When the report is knit, the results of these computations are inserted into the text:

We have data about 53940 diamonds. Only 126 are larger than 2.5 carats. The distribution of the remainder is shown below:

When inserting numbers into text, format() is your friend. It allows you to set the number of digits so you don’t print to a ridiculous degree of accuracy, and a big.mark to make numbers easier to read. I’ll often combine these into a helper function:

```r
comma <- function(x) format(x, digits = 2, big.mark = ",")
comma(3452345)
#> [1] "3,452,345"
comma(.12358124331)
#> [1] "0.12"
```

27.5
Ctrl + Alt + R = reruns all code chunks

Check the working directory is what you expect by including getwd() in a chunk.

error = TRUE on the chunk causing the problem, then use print() and str() to check that settings are as you expect

27.6 YAML header
27.6.1.
You can also run arbitrary R expressions by prefacing the parameter value with !r. This is a good way to specify date/time parameters.

```r
params:
  start: !r lubridate::ymd("2015-01-01")
  snapshot: !r lubridate::ymd_hms("2015-01-01 12:30:00")
```

```r
rmarkdown::render("fuel-economy.Rmd", params = list(my_class = "suv"))
```

purrr:pwalk()

```r
reports <- tibble(
  class = unique(mpg$class),
  filename = stringr::str_c("fuel-economy-", class, ".html"),
  params = purrr::map(class, ~ list(my_class = .))
)
reports
#> # A tibble: 7 × 3
#>   class   filename                  params          
#>   <chr>   <chr>                     <list>          
#> 1 compact fuel-economy-compact.html <named list [1]>
#> 2 midsize fuel-economy-midsize.html <named list [1]>
#> 3 suv     fuel-economy-suv.html     <named list [1]>
#> 4 2seater fuel-economy-2seater.html <named list [1]>
#> 5 minivan fuel-economy-minivan.html <named list [1]>
#> 6 pickup  fuel-economy-pickup.html  <named list [1]>
#> # … with 1 more row
```

Then we match the column names to the argument names of render(), and use purrr’s parallel walk to call render() once for each row:

reports %>% 
  select(output_file = filename, params) %>% 
  purrr::pwalk(rmarkdown::render, input = "fuel-economy.Rmd")

  The code first selects the output_file and params columns from the reports data frame. The output_file column contains the filename of the report to be generated, and the params column contains a list of parameters that will be passed to the report template.


Sure, the code you provided is a pipe expression in the R programming language. It uses the purrr and rmarkdown packages to generate a set of reports from a data frame.

The code first selects the output_file and params columns from the reports data frame. The output_file column contains the filename of the report to be generated, and the params column contains a list of parameters that will be passed to the report template.

The purrr::pwalk() function then iterates over the rows of the reports data frame, calling the rmarkdown::render() function for each row. The rmarkdown::render() function takes two arguments: the path to the report template and the list of parameters.

In this case, the report template is located at fuel-economy.Rmd. The params list contains the output_file and params columns from the reports data frame.

The pwalk() function will call the rmarkdown::render() function for each row of the reports data frame, generating a separate report for each row. The filename of each report will be the value of the output_file column for that row.

reports: This is a data frame that contains the information for the reports to be generated.
select(): This function selects the output_file and params columns from the reports data frame.
purrr::pwalk(): This function iterates over the rows of the reports data frame, calling the rmarkdown::render() function for each row.
rmarkdown::render(): This function generates a report from a report template and a list of parameters.

27.6.2 Bibliographies and Citations

```YAML
bibliography: rmarkdown.bib
```
You can use many common bibliography formats including BibLaTeX, BibTeX, endnote, medline.

To create a citation within your .Rmd file, use a key composed of ‘@’ + the citation identifier from the bibliography file. Then place the citation in square brackets. Here are some examples:

Separate multiple citations with a `;`: Blah blah [@smith04; @doe99].
You can add arbitrary comments inside the square brackets: 
Blah blah [see @doe99, pp. 33-35; also @smith04, ch. 1].

Remove the square brackets to create an in-text citation: @smith04 
says blah, or @smith04 [p. 33] says blah.

Add a `-` before the citation to suppress the author's name: 
Smith says blah [-@smith04].

When R Markdown renders your file, it will build and append a bibliography to the end of your document. The bibliography will contain each of the cited references from your bibliography file, but it will not contain a section heading.

As a result it is common practice to end your file with a section header for the bibliography, such as # References or # Bibliography.

```YAML
bibliography: rmarkdown.bib
csl: apa.csl
```
http://github.com/citation-style-language/styles

27.7 Learning more
“Happy Git with R”: a user friendly introduction to Git and GitHub from R users, by Jenny Bryan. The book is freely available online: http://happygitwithr.com

The “Git and GitHub” chapter of R Packages, by Hadley. You can also read it for free online: http://r-pkgs.had.co.nz/git.html.

Style: Lessons in Clarity and Grace by Joseph M. Williams & Joseph Bizup, or The Sense of Structure: Writing from the Reader’s Perspective by George Gopen

 George Gopen also has a number of short articles on writing at https://www.georgegopen.com/the-litigation-articles.html. 

### Creating an RMarkdown Document

2023 Jul 5
https://www.coursera.org/learn/r-programming-tidyverse/supplement/xTcpc/helpful-tips-and-resources-on-rmarkdown

