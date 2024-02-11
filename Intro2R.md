# Intro to Programming in R

This is an R tutorial largely sourced from
[Intro2R.com](https://intro2r.com/), which also contains further detail
about more complex programming capabilities. Feel free to check out the
site to explore other things you can do in R! Once you have a sense of
the basic syntax, R gives you a widely expansive, customizable, and
powerful set of tools for any sort of data manipulation, analysis, and
visualization. It can be intimidating to start with, but you don’t need
to learn every part of it to use it– real programmers are always
Googling “how do I do this particular task in R?”, and once you know the
very basics, you can understand all of the resources out there to help
you build your own code and programs.

A few points from Intro2R:

-   Use R often and use it regularly - find any excuse to fire up
    RStudio (or just R) and get coding. This will help build and
    maintain all important momentum.

-   Learning R is not a memory test. One of the beauties of a scripting
    language is that you will always have your code to refer back to
    when you inevitably forget how to do something.

-   You don’t need to know everything there is to know about R to use it
    productively. If you get stuck, Google it, it’s not cheating and
    writing a good search query is a skill in itself. Just make sure you
    check thoroughly that the code you find is doing what you want it to
    do.

-   If you find yourself staring at code for hours trying to figure out
    why it’s not working then walk away for a few minutes. We’ve lost
    count of the number of times we were able to spot our mistake almost
    immediately after returning from a short caffeine break.

-   In R there are many ways to tackle a particular problem. If your
    code doesn’t look like someone elses, but it does what you want it
    to do in a reasonable time and robustly then don’t worry about it -
    job done.

-   Related to our previous point, remember R is just a tool to help you
    answer your interesting questions. Although it can be fun to immerse
    yourself in all things R (we often do), don’t lose sight of what’s
    important - your research question(s) and your data. No amount of
    skill using R will help if your data collection is fundamentally
    flawed or your question vague.

-   Recognise that there will be times when things will get a little
    tough or frustrating. Try to accept these periods as part of the
    natural process of learning a new skill (we’ve all been there) and
    remember, the time and energy you invest now will be more than payed
    back in the not too distant future.

## Basics

At a basic level we can use R much as you would use a calculator. We can
type an arithmetic expression into our script, then source it into the
console and receive a result. For example, if we type the expression 2 +
2 and then source this line of code we get the answer 4.

    2+2

    ## [1] 4

The \[1\] in front of the result tells you that the observation number
at the beginning of the line is the first observation. This is not much
help in this example, but can be quite useful when printing results with
multiple lines (we’ll see an example below). The other obvious
arithmetic operators are -, `*`, / for subtraction, multiplication and
division respectively. R follows the usual mathematical convention of
order of operations. For example, the expression 2 + 3 \* 4 is
interpreted to have the value 2 + (3 \* 4) = 14, not (2 + 3) \* 4 = 20.
There are a huge range of mathematical functions in R, some of the most
useful include; log(), log10(), exp(), sqrt().

    log(1)

    ## [1] 0

    exp(1)

    ## [1] 2.718282

    sqrt(4)

    ## [1] 2

    2^2

    ## [1] 4

    pi

    ## [1] 3.141593

Try experimenting with this so you get familiar with the operations. In
the box below, write some arithmetic operations, and see that you get
results that make sense. Note that in the box below, some text is
following the “\#” symbol, and is greyed-out. This is “comment” text.
When text is written as a comment, it tells R not to run it as code;
this allows us to write annotations, intructions, or descriptions
in-line with the code, to make it more understandable. Adding a “\#” to
a line of text is called “commenting out” a line.

    #add your own arithmetic operations here, below this line

## Objects in R

At the heart of almost everything you will do (or ever likely to do) in
R is the concept that everything in R is an object. These objects can be
almost anything, from a single number or character string (like a word)
to highly complex structures like the output of a plot, a summary of
your statistical analysis or a set of R commands that perform a specific
task. Understanding how you create objects and assign values to objects
is key to understanding R.

To create an object we simply give the object a name. We can then assign
a value to this object using the assignment operator &lt;- (sometimes
called the gets operator). The assignment operator is a composite symbol
comprised of a ‘less than’ symbol &lt; and a hyphen - .

In the code above, we created an object called my\_obj and assigned it a
value of the number 48 using the assignment operator (in our head we
always read this as ‘my\_obj gets 48’). You can also use = instead of
&lt;- to assign values but this is considered bad practice and we would
discourage you from using this notation.

    my_obj<-48

    my_obj

    ## [1] 48

Now that we’ve created this object, R knows all about it and will keep
track of it during this current R session. All of the objects you create
will be stored in the current workspace and you can view all the objects
in your workspace in RStudio by clicking on the ‘Environment’ tab in the
top right hand pane.

If you click on the down arrow on the ‘List’ icon in the same pane and
change to ‘Grid’ view RStudio will show you a summary of the objects
including the type (numeric - it’s a number), the length (only one value
in this object), its ‘physical’ size and its value (48 in this case).

There are many different types of values that you can assign to an
object. For example

    my_obj2 <- "R is cool"

    my_obj2

    ## [1] "R is cool"

Here we have created an object called my\_obj2 and assigned it a value
of R is cool which is a character string. Notice that we have enclosed
the string in quotes. If you forget to use the quotes you will receive
an error message. Try removing the quotes here and see what happens.

    my_obj3 <- "R is cool"

    my_obj3

    ## [1] "R is cool"

To change the value of an existing object we simply reassign a new value
to it. For example, to change the value of my\_obj2 from “R is cool” to
the number 1024

    my_obj2 <- 1024

    my_obj2

    ## [1] 1024

Try creating your own objects here. Try creating a numeric object and a
character object, and then “call” those objects (i.e., write their
names, and run the code) to see that R returns the correct values of
these objects.

    #create a numeric object brlow


    #call the object below


    #create a character object below


    #call the object below

Once we have created a few objects, we can do stuff with our objects.
For example, the following code creates a new object my\_obj3 and
assigns it the value of my\_obj added to my\_obj2 which is 1072 (48 +
1024 = 1072).

    my_obj3 <- my_obj + my_obj2

    my_obj3

    ## [1] 1072

Notice that to display the value of my\_obj3 we also need to write the
object’s name. The above code works because the values of both my\_obj
and my\_obj2 are numeric (i.e. a number). If you try to do this with
objects with character values (character class) you will receive an
error. Try creating an object called “char\_obj3” by adding “char\_obj”
and “char\_obj2” together, and see what happens.

    char_obj <- "hello"
    char_obj2 <- "world!"

    #your code below

Naming your objects is one of the most difficult things you will do in R
(honestly - we’re serious). Ideally your object names should be kept
both short and informative which is not always easy. If you need to
create objects with multiple words in their name then use either an
underscore or a dot between words or capitalise the different words. We
prefer the underscore format (called snake case)

output\_summary &lt;- “my analysis” output.summary &lt;- “my analysis”
outputSummary &lt;- “my analysis” There are also a few limitations when
it come to giving objects names. An object name cannot start with a
number or a dot followed by a number (i.e. 2my\_variable or
.2my\_variable). You should also avoid using non-alphanumeric characters
in your object names (i.e. &, ^, /, ! etc). In addition, make sure you
don’t name your objects with reserved words (i.e. TRUE, NA) and it’s
never a good idea to give your object the same name as a built-in
function.

## Functions in R

Up until now we’ve been creating simple objects by directly assigning a
single value to an object. It’s very likely that you’ll soon want to
progress to creating more complicated objects as your R experience grows
and the complexity of your tasks increase. Happily, R has a multitude of
functions to help you do this. You can think of a function as an object
which contains a series of instructions to perform a specific task. The
base installation of R comes with many functions already defined or you
can increase the power of R by installing one of the 10000’s of packages
now available. Once you get a bit more experience with using R you may
want to define your own functions to perform tasks that are specific to
your goals.

## Built-In Functions

The first function we will learn about is the c() function. The c()
function is short for concatenate and we use it to join together a
series of values and store them in a data structure called a vector.

    my_vec <- c(2, 3, 1, 6, 4, 3, 3, 7)

In the code above we’ve created an object called my\_vec and assigned it
a value using the function c(). There are a couple of really important
points to note here. Firstly, when you use a function in R, the function
name is always followed by a pair of round brackets even if there’s
nothing contained between the brackets. Secondly, the argument(s) of a
function are placed inside the round brackets and are separated by
commas. You can think of an argument as way of customising the use or
behaviour of a function. In the example above, the arguments are the
numbers we want to concatenate. Finally, one of the tricky things when
you first start using R is to know which function to use for a
particular task and how to use it. Thankfully each function will always
have a help document associated with it which will explain how to use
the function (more on this later) and a quick Google search will also
usually help you out.

To examine the value of our new object we can simply type out the name
of the object as we did before.

    my_vec

    ## [1] 2 3 1 6 4 3 3 7

Now that we’ve created a vector we can use other functions to do useful
stuff with this object. For example, we can calculate the mean,
variance, standard deviation and number of elements in our vector by
using the mean(), var(), sd() and length() functions

    mean(my_vec)    # returns the mean of my_vec

    ## [1] 3.625

    var(my_vec)     # returns the variance of my_vec

    ## [1] 3.982143

    sd(my_vec)      # returns the standard deviation of my_vec

    ## [1] 1.995531

    length(my_vec)  # returns the number of elements in my_vec

    ## [1] 8

If we wanted to use any of these values later on in our analysis we can
just assign the resulting value to another object

    vec_mean <- mean(my_vec)    # returns the mean of my_vec
    vec_mean

    ## [1] 3.625

Sometimes it can be useful to create a vector that contains a regular
sequence of values in steps of one. Here we can make use of a shortcut
using the : symbol. Other useful functions for generating vectors of
sequences include the seq() and rep() functions. For example, to
generate a sequence from 1 to 5 in steps of 0.5

    my_seq <- 1:10     # create regular sequence
    my_seq

    ##  [1]  1  2  3  4  5  6  7  8  9 10

    my_seq2 <- 10:1    # in decending order
    my_seq2

    ##  [1] 10  9  8  7  6  5  4  3  2  1

    my_seq2 <- seq(from = 1, to = 5, by = 0.5)
    my_seq2

    ## [1] 1.0 1.5 2.0 2.5 3.0 3.5 4.0 4.5 5.0

Here we’ve used the arguments from = and to = to define the limits of
the sequence and the by = argument to specify the increment of the
sequence. Play around with other values for these arguments to see their
effect. The rep() function allows you to replicate (repeat) values a
specified number of times. You can also repeat non-numeric values, or
each element of a series, or elements of a series, or each element of a
series.

    my_seq3 <- rep(2, times = 10)   # repeats 2, 10 times
    my_seq3

    ##  [1] 2 2 2 2 2 2 2 2 2 2

    my_seq4 <- rep("abc", times = 3)    # repeats ‘abc’ 3 times 
    my_seq4

    ## [1] "abc" "abc" "abc"

    my_seq5 <- rep(1:5, times = 3)  # repeats the series 1 to 5, 3 times
    my_seq5

    ##  [1] 1 2 3 4 5 1 2 3 4 5 1 2 3 4 5

    my_seq6 <- rep(1:5, each = 3)   # repeats each element of the series 3 times
    my_seq6

    ##  [1] 1 1 1 2 2 2 3 3 3 4 4 4 5 5 5

We can also repeat a non-sequential series

    my_seq7 <- rep(c(3, 1, 10, 7), each = 3) # repeats each 
                                             # element of the 
                                             # series 3 times
    my_seq7

    ##  [1]  3  3  3  1  1  1 10 10 10  7  7  7

Note in the code above how we’ve used the c() function inside the rep()
function. Nesting functions allows us to build quite complex commands
within a single line of code and is a very common practice when using R.
However, care needs to be taken as too many nested functions can make
your code quite difficult for others to understand (or yourself some
time in the future!). We could rewrite the code above to explicitly
separate the two different steps to generate our vector. Either approach
will give the same result, you just need to use your own judgement as to
which is more readable.

    in_vec <- c(3, 1, 10, 7)
    my_seq7 <- rep(in_vec, each = 3)    # repeats each element of 
                                      # the series 3 times
    my_seq7

    ##  [1]  3  3  3  1  1  1 10 10 10  7  7  7

## Custom Functions

R has lots of built-in functions, and more can be added through packages
(we’ll explain packages below). To use built-in functions (or those
loaded through packages), we’ve seen that we “call” them with the
notation function(), and arguments to the function. But we can also
build our own.

A function takes an object and does something to it. This is just like
in math class, where a function f(x) takes x and does some operation to
it. In the function f(x)=x+1, f() takes a number x, and adds 1 to it, so
that f(3)=4. This is just the same in R. Let’s build a function that
takes an input, multiplies it by 3, and subtracts 2. We use the notation
function(x), where x is an argument to the function. The function is
then defined in curly brackets. So, it would look like:

    my_function<-function(x){x*3-2}

Now, we can use this function, with different arguments (a.k.a. inputs
to the function)

    my_function(x=1)

    ## [1] 1

    my_function(x=-2)

    ## [1] -8

    my_function(x=pi)

    ## [1] 7.424778

We can make functions take multiple arguments. Let’s make a function to
take a number, multiply it by 2, take another number multiplied by 3,
and add them together.

    my_function_2<-function(x, y){x*2 + y*3}

    my_function_2(x=1, y=1)

    ## [1] 5

    my_function_2(x=1, y=2)

    ## [1] 8

    my_function_2(x=25, y=100)

    ## [1] 350

What we name variables is arbitrary; we just use these to help
understand the function. What the variables do is defined by the
function. So, we could also write the above function like:

    my_function_3<-function(input1, input2){input1*2 + input2*3}

    my_function_3(input1=25, input2=100)

    ## [1] 350

In fact, we don’t even need to specify the variable names in the
function call. However, it is *very* helpful to do so, especially when
you’re new to using a function, in order to keep track of which
arguments are which, and make sure they’re doing the things you want
them to do. But, it can work without them:

    my_function_2(25, 100)

    ## [1] 350

Try writing your own function that squares a number and adds 10.

    #your function below

All of the functions built into R or loaded through packages are written
in this format, using basic data operations and stitching them together.
For example, you can view the “source code” of the sd() function, which
returns standard deviation of an input vector. We can use print() to
have the console display some item, and see what sd() is doing under the
hood. Don’t mind all of the detail for now, but you can see that sd() is
taking a variable x, and finding the square root of its variance. This
is the kind of thing that happens any time you use any function.

    print(sd)

    ## function (x, na.rm = FALSE) 
    ## sqrt(var(if (is.vector(x) || is.factor(x)) x else as.double(x), 
    ##     na.rm = na.rm))
    ## <bytecode: 0x7f7cabe8cae0>
    ## <environment: namespace:stats>

## Vectors

We made and used some vectors above. Vectors are an important data
structure in R, and we will now explore them in more detail.

### Extracting Elements

To extract (also known as indexing or subscripting) one or more values
(more generally known as elements) from a vector we use the square
bracket \[ \] notation. The general approach is to name the object you
wish to extract from, then a set of square brackets with an index of the
element you wish to extract contained within the square brackets. This
index can be a position or the result of a logical test.

To extract elements based on their position we simply write the position
inside the \[ \]. For example, to extract the 3rd value of my\_vec

    my_vec        # remind ourselves what my_vec looks like

    ## [1] 2 3 1 6 4 3 3 7

    my_vec[3]     # extract the 3rd value

    ## [1] 1

    # if you want to store this value in another object
    val_3 <- my_vec[3]
    val_3

    ## [1] 1

Note that the positional index starts at 1 rather than 0 like some other
other programming languages (i.e. Python).

We can also extract more than one value by using the c() function inside
the square brackets. Here we extract the 1st, 5th, 6th and 8th element
from the my\_vec object. Or we can extract a range of values using the :
notation. To extract the values from the 3rd to the 8th elements.

    my_vec[c(1, 5, 6, 8)]

    ## [1] 2 4 3 7

    my_vec[3:8]

    ## [1] 1 6 4 3 3 7

Another really useful way to extract data from a vector is to use a
logical expression as an index. For example, to extract all elements
with a value greater than 4 in the vector my\_vec

    my_vec[my_vec > 4]

    ## [1] 6 7

Here, the logical expression is my\_vec &gt; 4 and R will only extract
those elements that satisfy this logical condition. So how does this
actually work? If we look at the output of just the logical expression
without the square brackets you can see that R returns a vector
containing either TRUE or FALSE which correspond to whether the logical
condition is satisfied for each element. In this case only the 4th and
8th elements return a TRUE as their value is greater than 4.

    my_vec > 4

    ## [1] FALSE FALSE FALSE  TRUE FALSE FALSE FALSE  TRUE

So what R is actually doing under the hood is equivalent to

    my_vec[c(FALSE, FALSE, FALSE, TRUE, FALSE, FALSE, FALSE, TRUE)]

    ## [1] 6 7

and only those element that are TRUE will be extracted.

In addition to the &lt; and &gt; operators you can also use composite
operators to increase the complexity of your expressions. For example
the expression for ‘greater or equal to’ is &gt;=. To test whether a
value is equal to a value we need to use a double equals symbol == and
for ‘not equal to’ we use != (the ! symbol means ‘not’).

    my_vec[my_vec >= 4]        # values greater or equal to 4

    ## [1] 6 4 7

    my_vec[my_vec < 4]         # values less than 4

    ## [1] 2 3 1 3 3

    my_vec[my_vec <= 4]        # values less than or equal to 4

    ## [1] 2 3 1 4 3 3

    my_vec[my_vec == 4]        # values equal to 4

    ## [1] 4

    my_vec[my_vec != 4]        # values not equal to 4

    ## [1] 2 3 1 6 3 3 7

Try writing your own code here to extract the values of my\_vec that are
equal to 3:

    #your code here

We can also combine multiple logical expressions using Boolean
expressions. In R the & symbol means AND and the | symbol means OR. For
example, to extract values in my\_vec which are less than 6 AND greater
than 2

    val26 <- my_vec[my_vec < 6 & my_vec > 2]
    val26

    ## [1] 3 4 3 3

or extract values in my\_vec that are greater than 6 OR less than 3

    val63 <- my_vec[my_vec > 6 | my_vec < 3]
    val63

    ## [1] 2 1 7

### Replacing and Ordering Elements

We can change the values of some elements in a vector using our \[ \]
notation in combination with the assignment operator &lt;-. For example,
to replace the 4th value of our my\_vec object from 6 to 500

    my_vec

    ## [1] 2 3 1 6 4 3 3 7

    my_vec[4] <- 500

    my_vec

    ## [1]   2   3   1 500   4   3   3   7

We can also replace more than one value or even replace values based on
a logical expression

    # replace the 6th and 7th element with 100
    my_vec[c(6, 7)] <- 100
    my_vec

    ## [1]   2   3   1 500   4 100 100   7

    # replace element that are less than or equal to 4 with 1000
    my_vec[my_vec <= 4] <- 1000
    my_vec

    ## [1] 1000 1000 1000  500 1000  100  100    7

In addition to extracting particular elements from a vector we can also
order the values contained in a vector. To sort the values from lowest
to highest value we can use the sort() function

    vec_sort <- sort(my_vec)
    vec_sort

    ## [1]    7  100  100  500 1000 1000 1000 1000

To reverse the sort, from highest to lowest, we can either include the
decreasing = TRUE argument when using the sort() function, or first sort
the vector using the sort() function and then reverse the sorted vector
using the rev() function. This is another example of nesting one
function inside another function.

    vec_sort2 <- sort(my_vec, decreasing = TRUE)
    vec_sort2

    ## [1] 1000 1000 1000 1000  500  100  100    7

    vec_sort3 <- rev(sort(my_vec))
    vec_sort3

    ## [1] 1000 1000 1000 1000  500  100  100    7

Whilst sorting a single vector is fun, perhaps a more useful task would
be to sort one vector according to the values of another vector. To do
this we should use the order() function in combination with \[ \]. To
demonstrate this let’s create a vector called height containing the
height of 5 different people and another vector called p.names
containing the names of these people (so Joanna is 180 cm, Charlotte is
155 cm etc)

    height <- c(180, 155, 160, 167, 181)
    height

    ## [1] 180 155 160 167 181

    p.names <- c("Joanna", "Charlotte", "Helen", "Karen", "Amy")
    p.names

    ## [1] "Joanna"    "Charlotte" "Helen"     "Karen"     "Amy"

Our goal is to order the people in p.names in ascending order of their
height. The first thing we’ll do is use the order() function with the
height variable to create a vector called height\_ord

    height_ord <- order(height)
    height_ord

    ## [1] 2 3 4 1 5

OK, what’s going on here? The first value, 2, (remember ignore \[1\])
should be read as ‘the smallest value of height is the second element of
the height vector’. If we check this by looking at the height vector
above, you can see that element 2 has a value of 155, which is the
smallest value. The second smallest value in height is the 3rd element
of height, which when we check is 160 and so on. The largest value of
height is element 5 which is 181. Now that we have a vector of the
positional indices of heights in ascending order (height\_ord), we can
extract these values from our p.names vector in this order

    names_ord <- p.names[height_ord]
    names_ord

    ## [1] "Charlotte" "Helen"     "Karen"     "Joanna"    "Amy"

You’re probably thinking ‘what’s the use of this?’ Well, imagine you
have a dataset which contains two columns of data and you want to sort
each column. If you just use sort() to sort each column separately, the
values of each column will become uncoupled from each other. By using
the ‘order()’ on one column, a vector of positional indices is created
of the values of the column in ascending order This vector can be used
on the second column, as the index of elements which will return a
vector of values based on the first column.

### Vectorization

One of the great things about R functions is that most of them are
vectorised. This means that the function will operate on all elements of
a vector without needing to apply the function on each element
separately. For example, to multiple each element of a vector by 5 we
can simply use

    # create a vector
    my_vec2 <- c(3, 5, 7, 1, 9, 20)

    # multiply each element by 5
    my_vec2 * 5

    ## [1]  15  25  35   5  45 100

Or we can add the elements of two or more vectors

    # create a second vector
    my_vec3 <- c(17, 15, 13, 19, 11, 0)

    # add both vectors
    my_vec2 + my_vec3

    ## [1] 20 20 20 20 20 20

    # multiply both vectors
    my_vec2 * my_vec3

    ## [1] 51 75 91 19 99  0

However, you must be careful when using vectorisation with vectors of
different lengths as R will quietly recycle the elements in the shorter
vector rather than throw a wobbly (error).

    # create a third vector
    my_vec4 <- c(1, 2)

    # add both vectors - quiet recycling!
    my_vec2 + my_vec4

    ## [1]  4  7  8  3 10 22

### Missing Data

In R, missing data is usually represented by an NA symbol meaning ‘Not
Available’. Data may be missing for a whole bunch of reasons, maybe your
machine broke down, maybe you broke down, maybe the weather was too bad
to collect data on a particular day etc etc. Missing data can be a pain
in the proverbial both from an R perspective and also a statistical
perspective. From an R perspective missing data can be problematic as
different functions deal with missing data in different ways. For
example, let’s say we collected air temperature readings over 10 days,
but our thermometer broke on day 2 and again on day 9 so we have no data
for those days. We now want to calculate the mean temperature over these
days using the mean() function.

    temp  <- c(7.2, NA, 7.1, 6.9, 6.5, 5.8, 5.8, 5.5, NA, 5.5)
    temp

    ##  [1] 7.2  NA 7.1 6.9 6.5 5.8 5.8 5.5  NA 5.5

    mean_temp <- mean(temp)
    mean_temp

    ## [1] NA

What’s happened here? Why does the mean() function return an NA?
Actually, R is doing something very sensible (at least in our opinion!).
If a vector has a missing value then the only possible value to return
when calculating a mean is NA. R doesn’t know that you perhaps want to
ignore the NA values (R can’t read your mind - yet!). Happily, if we
look at the help file (use help(“mean”) associated with the mean()
function we can see there is an argument na.rm = which is set to FALSE
by default.

    help("mean")

    ?mean()

    ?mean

If we change this argument to na.rm = TRUE when we use the mean()
function this will allow us to ignore the NA values when calculating the
mean

It’s important to note that the NA values have not been removed from our
temp object (that would be bad practice), rather the mean() function has
just ignored them. The point of the above is to highlight how we can
change the default behaviour of a function using an appropriate
argument. The problem is that not all functions will have an na.rm =
argument, they might deal with NA values differently. However, the good
news is that every help file associated with any function will always
tell you how missing data are handled by default.

## Data Types

R is able to store several types of data:

-   Numeric data are numbers that contain a decimal. Actually they can
    also be whole numbers but we’ll gloss over that.

-   Integers are whole numbers (those numbers without a decimal point).

-   Logical data take on the value of either TRUE or FALSE. There’s also
    another special type of logical called NA to represent missing
    values.

-   Character data are used to represent string values. You can think of
    character strings as something like a word (or multiple words). A
    special type of character string is a factor, which is a string but
    with additional attributes (like levels or an order). We’ll cover
    factors later.

-   Complex numbers (we will skip this for now).

-   Raw data (we will skip this for now, too).

R is (usually) able to automatically distinguish between different
classes of data by their nature and the context in which they’re used
although you should bear in mind that R can’t actually read your mind
and you may have to explicitly tell R how you want to treat a data type.
You can find out the type (or class) of any object using the class()
function.

    num <- 2.2
    class(num)

    ## [1] "numeric"

    char <- "hello"
    class(char)

    ## [1] "character"

    logi <- TRUE
    class(logi)

    ## [1] "logical"

Alternatively, you can ask if an object is a specific class using using
a logical test. The is.[classOfData]() family of functions will return
either a TRUE or a FALSE.

    is.numeric(num)

    ## [1] TRUE

    is.character(num)

    ## [1] FALSE

    is.character(char)

    ## [1] TRUE

    is.logical(logi)

    ## [1] TRUE

It can sometimes be useful to be able to change the class of a variable
using the as.[className]() family of coercion functions, although you
need to be careful when doing this as you might receive some unexpected
results (see what happens below when we try to convert a character
string to a numeric).

    # coerce numeric to character
    class(num)

    ## [1] "numeric"

    num_char <-  as.character(num)
    num_char

    ## [1] "2.2"

    class(num_char)

    ## [1] "character"

    # coerce character to numeric!
    class(char)

    ## [1] "character"

    #try this one and see what happens
    char_num <- as.numeric(char)

    ## Warning: NAs introduced by coercion

Perhaps the simplest type of data structure is the vector. You’ve
already been introduced to vectors, although some of the vectors you
created only contained a single value. Vectors that have a single value
(length 1) are called scalars. Vectors can contain numbers, characters,
factors or logicals, but the key thing to remember is that all the
elements inside a vector must be of the same class. In other words,
vectors can contain either numbers, characters or logicals but not
mixtures of these types of data. There is one important exception to
this, you can include NA (remember this is special type of logical) to
denote missing data in vectors with other data types.

Another useful data structure used in many disciplines such as
population ecology, theoretical and applied statistics is the matrix. A
matrix is simply a vector that has additional attributes called
dimensions. Arrays are just multidimensional matrices. Again, matrices
and arrays must contain elements all of the same data class.

### Matrices, Scalars, Arrays and Lists

A convenient way to create a matrix or an array is to use the matrix()
and array() functions respectively. Below, we will create a matrix from
a sequence 1 to 16 in four rows (nrow = 4) and fill the matrix row-wise
(byrow = TRUE) rather than the default column-wise. When using the
array() function we define the dimensions using the dim = argument, in
our case 2 rows, 4 columns in 2 different matrices.

    my_mat <- matrix(1:16, nrow = 4, byrow = TRUE)
    my_mat

    ##      [,1] [,2] [,3] [,4]
    ## [1,]    1    2    3    4
    ## [2,]    5    6    7    8
    ## [3,]    9   10   11   12
    ## [4,]   13   14   15   16

    my_array <- array(1:16, dim = c(2, 4, 2))
    my_array

    ## , , 1
    ## 
    ##      [,1] [,2] [,3] [,4]
    ## [1,]    1    3    5    7
    ## [2,]    2    4    6    8
    ## 
    ## , , 2
    ## 
    ##      [,1] [,2] [,3] [,4]
    ## [1,]    9   11   13   15
    ## [2,]   10   12   14   16

Sometimes it’s also useful to define row and column names for your
matrix but this is not a requirement. To do this use the rownames() and
colnames() functions.

    rownames(my_mat) <- c("A", "B", "C", "D")
    colnames(my_mat) <- c("a", "b", "c", "d")
    my_mat

    ##    a  b  c  d
    ## A  1  2  3  4
    ## B  5  6  7  8
    ## C  9 10 11 12
    ## D 13 14 15 16

Once you’ve created your matrices you can do useful stuff with them and
as you’d expect, R has numerous built in functions to perform matrix
operations. Some of the most common are given below. For example, to
transpose a matrix we use the transposition function t() To extract the
diagonal elements of a matrix and store them as a vector we can use the
diag() function.

    my_mat_t <- t(my_mat)
    my_mat_t

    ##   A B  C  D
    ## a 1 5  9 13
    ## b 2 6 10 14
    ## c 3 7 11 15
    ## d 4 8 12 16

    my_mat_diag <- diag(my_mat)
    my_mat_diag

    ## [1]  1  6 11 16

The usual matrix addition, multiplication etc can be performed. Note the
use of the %\*% operator to perform matrix multiplication.

    mat.1 <- matrix(c(2, 0, 1, 1), nrow = 2)    # notice that the matrix has been filled 
    mat.1                                     # column-wise by default

    ##      [,1] [,2]
    ## [1,]    2    1
    ## [2,]    0    1

    mat.2 <- matrix(c(1, 1, 0, 2), nrow = 2)
    mat.2

    ##      [,1] [,2]
    ## [1,]    1    0
    ## [2,]    1    2

    mat.1 + mat.2           # matrix addition

    ##      [,1] [,2]
    ## [1,]    3    1
    ## [2,]    1    3

    mat.1 * mat.2           # element by element products

    ##      [,1] [,2]
    ## [1,]    2    0
    ## [2,]    0    2

    mat.1 %*% mat.2         # matrix multiplication

    ##      [,1] [,2]
    ## [1,]    3    2
    ## [2,]    1    2

### Lists

The next data structure we will quickly take a look at is a list. Whilst
vectors and matrices are constrained to contain data of the same type,
lists are able to store mixtures of data types. In fact we can even
store other data structures such as vectors and arrays within a list or
even have a list of a list. This makes for a very flexible data
structure which is ideal for storing irregular or non-rectangular data.
To create a list we can use the list() function. Note how each of the
three list elements are of different classes (character, logical, and
numeric) and are of different lengths.

    list_1 <- list(c("black", "yellow", "orange"),
                   c(TRUE, TRUE, FALSE, TRUE, FALSE, FALSE),
                   matrix(1:6, nrow = 3))
    list_1

    ## [[1]]
    ## [1] "black"  "yellow" "orange"
    ## 
    ## [[2]]
    ## [1]  TRUE  TRUE FALSE  TRUE FALSE FALSE
    ## 
    ## [[3]]
    ##      [,1] [,2]
    ## [1,]    1    4
    ## [2,]    2    5
    ## [3,]    3    6

Elements of the list can be named during the construction of the list,
or after the list has been created using the names() function.

    list_2 <- list(colours = c("black", "yellow", "orange"), 
                   evaluation = c(TRUE, TRUE, FALSE, TRUE, FALSE, FALSE), 
                   time = matrix(1:6, nrow = 3))
    list_2

    ## $colours
    ## [1] "black"  "yellow" "orange"
    ## 
    ## $evaluation
    ## [1]  TRUE  TRUE FALSE  TRUE FALSE FALSE
    ## 
    ## $time
    ##      [,1] [,2]
    ## [1,]    1    4
    ## [2,]    2    5
    ## [3,]    3    6

    names(list_1) <- c("colours", "evaluation", "time")
    list_1

    ## $colours
    ## [1] "black"  "yellow" "orange"
    ## 
    ## $evaluation
    ## [1]  TRUE  TRUE FALSE  TRUE FALSE FALSE
    ## 
    ## $time
    ##      [,1] [,2]
    ## [1,]    1    4
    ## [2,]    2    5
    ## [3,]    3    6

## Data Frames

By far the most commonly used data structure to store data in is the
data frame. A data frame is a powerful two-dimensional object made up of
rows and columns which looks superficially very similar to a matrix.
However, whilst matrices are restricted to containing data all of the
same type, data frames can contain a mixture of different types of data.
Typically, in a data frame each row corresponds to an individual
observation and each column corresponds to a different measured or
recorded variable. This setup may be familiar to those of you who use
LibreOffice Calc or Microsoft Excel to manage and store your data.
Perhaps a useful way to think about data frames is that they are
essentially made up of a bunch of vectors (columns) with each vector
containing its own data type but the data type can be different between
vectors.

Here is an example dataframe in R, built-in to the language as an
example:

    iris

    ##     Sepal.Length Sepal.Width Petal.Length Petal.Width    Species
    ## 1            5.1         3.5          1.4         0.2     setosa
    ## 2            4.9         3.0          1.4         0.2     setosa
    ## 3            4.7         3.2          1.3         0.2     setosa
    ## 4            4.6         3.1          1.5         0.2     setosa
    ## 5            5.0         3.6          1.4         0.2     setosa
    ## 6            5.4         3.9          1.7         0.4     setosa
    ## 7            4.6         3.4          1.4         0.3     setosa
    ## 8            5.0         3.4          1.5         0.2     setosa
    ## 9            4.4         2.9          1.4         0.2     setosa
    ## 10           4.9         3.1          1.5         0.1     setosa
    ## 11           5.4         3.7          1.5         0.2     setosa
    ## 12           4.8         3.4          1.6         0.2     setosa
    ## 13           4.8         3.0          1.4         0.1     setosa
    ## 14           4.3         3.0          1.1         0.1     setosa
    ## 15           5.8         4.0          1.2         0.2     setosa
    ## 16           5.7         4.4          1.5         0.4     setosa
    ## 17           5.4         3.9          1.3         0.4     setosa
    ## 18           5.1         3.5          1.4         0.3     setosa
    ## 19           5.7         3.8          1.7         0.3     setosa
    ## 20           5.1         3.8          1.5         0.3     setosa
    ## 21           5.4         3.4          1.7         0.2     setosa
    ## 22           5.1         3.7          1.5         0.4     setosa
    ## 23           4.6         3.6          1.0         0.2     setosa
    ## 24           5.1         3.3          1.7         0.5     setosa
    ## 25           4.8         3.4          1.9         0.2     setosa
    ## 26           5.0         3.0          1.6         0.2     setosa
    ## 27           5.0         3.4          1.6         0.4     setosa
    ## 28           5.2         3.5          1.5         0.2     setosa
    ## 29           5.2         3.4          1.4         0.2     setosa
    ## 30           4.7         3.2          1.6         0.2     setosa
    ## 31           4.8         3.1          1.6         0.2     setosa
    ## 32           5.4         3.4          1.5         0.4     setosa
    ## 33           5.2         4.1          1.5         0.1     setosa
    ## 34           5.5         4.2          1.4         0.2     setosa
    ## 35           4.9         3.1          1.5         0.2     setosa
    ## 36           5.0         3.2          1.2         0.2     setosa
    ## 37           5.5         3.5          1.3         0.2     setosa
    ## 38           4.9         3.6          1.4         0.1     setosa
    ## 39           4.4         3.0          1.3         0.2     setosa
    ## 40           5.1         3.4          1.5         0.2     setosa
    ## 41           5.0         3.5          1.3         0.3     setosa
    ## 42           4.5         2.3          1.3         0.3     setosa
    ## 43           4.4         3.2          1.3         0.2     setosa
    ## 44           5.0         3.5          1.6         0.6     setosa
    ## 45           5.1         3.8          1.9         0.4     setosa
    ## 46           4.8         3.0          1.4         0.3     setosa
    ## 47           5.1         3.8          1.6         0.2     setosa
    ## 48           4.6         3.2          1.4         0.2     setosa
    ## 49           5.3         3.7          1.5         0.2     setosa
    ## 50           5.0         3.3          1.4         0.2     setosa
    ## 51           7.0         3.2          4.7         1.4 versicolor
    ## 52           6.4         3.2          4.5         1.5 versicolor
    ## 53           6.9         3.1          4.9         1.5 versicolor
    ## 54           5.5         2.3          4.0         1.3 versicolor
    ## 55           6.5         2.8          4.6         1.5 versicolor
    ## 56           5.7         2.8          4.5         1.3 versicolor
    ## 57           6.3         3.3          4.7         1.6 versicolor
    ## 58           4.9         2.4          3.3         1.0 versicolor
    ## 59           6.6         2.9          4.6         1.3 versicolor
    ## 60           5.2         2.7          3.9         1.4 versicolor
    ## 61           5.0         2.0          3.5         1.0 versicolor
    ## 62           5.9         3.0          4.2         1.5 versicolor
    ## 63           6.0         2.2          4.0         1.0 versicolor
    ## 64           6.1         2.9          4.7         1.4 versicolor
    ## 65           5.6         2.9          3.6         1.3 versicolor
    ## 66           6.7         3.1          4.4         1.4 versicolor
    ## 67           5.6         3.0          4.5         1.5 versicolor
    ## 68           5.8         2.7          4.1         1.0 versicolor
    ## 69           6.2         2.2          4.5         1.5 versicolor
    ## 70           5.6         2.5          3.9         1.1 versicolor
    ## 71           5.9         3.2          4.8         1.8 versicolor
    ## 72           6.1         2.8          4.0         1.3 versicolor
    ## 73           6.3         2.5          4.9         1.5 versicolor
    ## 74           6.1         2.8          4.7         1.2 versicolor
    ## 75           6.4         2.9          4.3         1.3 versicolor
    ## 76           6.6         3.0          4.4         1.4 versicolor
    ## 77           6.8         2.8          4.8         1.4 versicolor
    ## 78           6.7         3.0          5.0         1.7 versicolor
    ## 79           6.0         2.9          4.5         1.5 versicolor
    ## 80           5.7         2.6          3.5         1.0 versicolor
    ## 81           5.5         2.4          3.8         1.1 versicolor
    ## 82           5.5         2.4          3.7         1.0 versicolor
    ## 83           5.8         2.7          3.9         1.2 versicolor
    ## 84           6.0         2.7          5.1         1.6 versicolor
    ## 85           5.4         3.0          4.5         1.5 versicolor
    ## 86           6.0         3.4          4.5         1.6 versicolor
    ## 87           6.7         3.1          4.7         1.5 versicolor
    ## 88           6.3         2.3          4.4         1.3 versicolor
    ## 89           5.6         3.0          4.1         1.3 versicolor
    ## 90           5.5         2.5          4.0         1.3 versicolor
    ## 91           5.5         2.6          4.4         1.2 versicolor
    ## 92           6.1         3.0          4.6         1.4 versicolor
    ## 93           5.8         2.6          4.0         1.2 versicolor
    ## 94           5.0         2.3          3.3         1.0 versicolor
    ## 95           5.6         2.7          4.2         1.3 versicolor
    ## 96           5.7         3.0          4.2         1.2 versicolor
    ## 97           5.7         2.9          4.2         1.3 versicolor
    ## 98           6.2         2.9          4.3         1.3 versicolor
    ## 99           5.1         2.5          3.0         1.1 versicolor
    ## 100          5.7         2.8          4.1         1.3 versicolor
    ## 101          6.3         3.3          6.0         2.5  virginica
    ## 102          5.8         2.7          5.1         1.9  virginica
    ## 103          7.1         3.0          5.9         2.1  virginica
    ## 104          6.3         2.9          5.6         1.8  virginica
    ## 105          6.5         3.0          5.8         2.2  virginica
    ## 106          7.6         3.0          6.6         2.1  virginica
    ## 107          4.9         2.5          4.5         1.7  virginica
    ## 108          7.3         2.9          6.3         1.8  virginica
    ## 109          6.7         2.5          5.8         1.8  virginica
    ## 110          7.2         3.6          6.1         2.5  virginica
    ## 111          6.5         3.2          5.1         2.0  virginica
    ## 112          6.4         2.7          5.3         1.9  virginica
    ## 113          6.8         3.0          5.5         2.1  virginica
    ## 114          5.7         2.5          5.0         2.0  virginica
    ## 115          5.8         2.8          5.1         2.4  virginica
    ## 116          6.4         3.2          5.3         2.3  virginica
    ## 117          6.5         3.0          5.5         1.8  virginica
    ## 118          7.7         3.8          6.7         2.2  virginica
    ## 119          7.7         2.6          6.9         2.3  virginica
    ## 120          6.0         2.2          5.0         1.5  virginica
    ## 121          6.9         3.2          5.7         2.3  virginica
    ## 122          5.6         2.8          4.9         2.0  virginica
    ## 123          7.7         2.8          6.7         2.0  virginica
    ## 124          6.3         2.7          4.9         1.8  virginica
    ## 125          6.7         3.3          5.7         2.1  virginica
    ## 126          7.2         3.2          6.0         1.8  virginica
    ## 127          6.2         2.8          4.8         1.8  virginica
    ## 128          6.1         3.0          4.9         1.8  virginica
    ## 129          6.4         2.8          5.6         2.1  virginica
    ## 130          7.2         3.0          5.8         1.6  virginica
    ## 131          7.4         2.8          6.1         1.9  virginica
    ## 132          7.9         3.8          6.4         2.0  virginica
    ## 133          6.4         2.8          5.6         2.2  virginica
    ## 134          6.3         2.8          5.1         1.5  virginica
    ## 135          6.1         2.6          5.6         1.4  virginica
    ## 136          7.7         3.0          6.1         2.3  virginica
    ## 137          6.3         3.4          5.6         2.4  virginica
    ## 138          6.4         3.1          5.5         1.8  virginica
    ## 139          6.0         3.0          4.8         1.8  virginica
    ## 140          6.9         3.1          5.4         2.1  virginica
    ## 141          6.7         3.1          5.6         2.4  virginica
    ## 142          6.9         3.1          5.1         2.3  virginica
    ## 143          5.8         2.7          5.1         1.9  virginica
    ## 144          6.8         3.2          5.9         2.3  virginica
    ## 145          6.7         3.3          5.7         2.5  virginica
    ## 146          6.7         3.0          5.2         2.3  virginica
    ## 147          6.3         2.5          5.0         1.9  virginica
    ## 148          6.5         3.0          5.2         2.0  virginica
    ## 149          6.2         3.4          5.4         2.3  virginica
    ## 150          5.9         3.0          5.1         1.8  virginica

There are a couple of important things to bear in mind about data
frames. These types of objects are known as rectangular data (or tidy
data) as each column must have the same number of observations. Also,
any missing data should be recorded as an NA just as we did with our
vectors.

We can construct a data frame from existing data objects such as vectors
using the data.frame() function. As an example, let’s create three
vectors p.height, p.weight and p.names and include all of these vectors
in a data frame object called dataf.

    p.height <- c(180, 155, 160, 167, 181)
    p.weight <- c(65, 50, 52, 58, 70)
    p.names <- c("Joanna", "Charlotte", "Helen", "Karen", "Amy")

    dataf <- data.frame(height = p.height, weight = p.weight, names = p.names)
    dataf

    ##   height weight     names
    ## 1    180     65    Joanna
    ## 2    155     50 Charlotte
    ## 3    160     52     Helen
    ## 4    167     58     Karen
    ## 5    181     70       Amy

You’ll notice that each of the columns are named with variable name we
supplied when we used the data.frame() function. It also looks like the
first column of the data frame is a series of numbers from one to five.
Actually, this is not really a column but the name of each row. We can
check this out by getting R to return the dimensions of the dataf object
using the dim() function. We see that there are 5 rows and 3 columns.
Another really useful function which we use all the time is str() which
will return a compact summary of the structure of the data frame object
(or any object for that matter).

    dim(dataf)

    ## [1] 5 3

    str(dataf)   

    ## 'data.frame':    5 obs. of  3 variables:
    ##  $ height: num  180 155 160 167 181
    ##  $ weight: num  65 50 52 58 70
    ##  $ names : chr  "Joanna" "Charlotte" "Helen" "Karen" ...

The str() function gives us the data frame dimensions and also reminds
us that dataf is a data.frame type object. It also lists all of the
variables (columns) contained in the data frame, tells us what type of
data the variables contain and prints out the first five values. We
often copy this summary and place it in our R scripts with comments at
the beginning of each line so we can easily refer back to it whilst
writing our code.

Also notice that R has automatically decided that our p.names variable
should be a character (chr) class variable when we first created the
data frame. Whether this is a good idea or not will depend on how you
want to use this variable in later analysis. If we decide that this
wasn’t such a good idea we can change the default behaviour of the
data.frame() function by including the argument stringsAsFactors = TRUE.
Now our strings are automatically converted to factors.

    p.height <- c(180, 155, 160, 167, 181)
    p.weight <- c(65, 50, 52, 58, 70)
    p.names <- c("Joanna", "Charlotte", "Helen", "Karen", "Amy")

    dataf <- data.frame(height = p.height, weight = p.weight, names = p.names, 
                                            stringsAsFactors = TRUE)
    str(dataf)

    ## 'data.frame':    5 obs. of  3 variables:
    ##  $ height: num  180 155 160 167 181
    ##  $ weight: num  65 50 52 58 70
    ##  $ names : Factor w/ 5 levels "Amy","Charlotte",..: 4 2 3 5 1

## Importing Data

Data importation is best described with visual examples, as it uses
software and files outside R and the R/RStudio environment. A good
explanation is available
[here](https://intro2r.com/importing-data.html), although this example
suggests using tab-delimited data, when in fact a more common format in
ecology is comma-delimited data (a.k.a. comma-separated values, or a
.CSV file).

## Wrangling Data

Once you’re able to successfully import your data from an external file
into R our next task is to do something useful with our data. Working
with data is a fundamental skill which you’ll need to develop and get
comfortable with as you’ll likely do a lot of it during any project. The
good news is that R is especially good at manipulating, summarising and
visualising data. Manipulating data (often known as data wrangling or
munging) in R can at first seem a little daunting for the new user but
if you follow a few simple logical rules then you’ll quickly get the
hang of it, especially with some practice.

Let’s pretend we’ve imported the ‘iris’ dataset from an external file,
and we’ll use that for practice.

To access the data in any of the variables (columns) in our data frame
we can use the $ notation. For example, to access the species variable
in our iris data frame we can use ‘iris$Species’. This tells R that the
Species variable is contained within the data frame iris

    #remind ourselves the structure of the dataset
    #the function head() returns just the first parts of a vector, data, table, or dataframe
    head(iris)

    ##   Sepal.Length Sepal.Width Petal.Length Petal.Width Species
    ## 1          5.1         3.5          1.4         0.2  setosa
    ## 2          4.9         3.0          1.4         0.2  setosa
    ## 3          4.7         3.2          1.3         0.2  setosa
    ## 4          4.6         3.1          1.5         0.2  setosa
    ## 5          5.0         3.6          1.4         0.2  setosa
    ## 6          5.4         3.9          1.7         0.4  setosa

    #access the species 
    iris$Species

    ##   [1] setosa     setosa     setosa     setosa     setosa     setosa    
    ##   [7] setosa     setosa     setosa     setosa     setosa     setosa    
    ##  [13] setosa     setosa     setosa     setosa     setosa     setosa    
    ##  [19] setosa     setosa     setosa     setosa     setosa     setosa    
    ##  [25] setosa     setosa     setosa     setosa     setosa     setosa    
    ##  [31] setosa     setosa     setosa     setosa     setosa     setosa    
    ##  [37] setosa     setosa     setosa     setosa     setosa     setosa    
    ##  [43] setosa     setosa     setosa     setosa     setosa     setosa    
    ##  [49] setosa     setosa     versicolor versicolor versicolor versicolor
    ##  [55] versicolor versicolor versicolor versicolor versicolor versicolor
    ##  [61] versicolor versicolor versicolor versicolor versicolor versicolor
    ##  [67] versicolor versicolor versicolor versicolor versicolor versicolor
    ##  [73] versicolor versicolor versicolor versicolor versicolor versicolor
    ##  [79] versicolor versicolor versicolor versicolor versicolor versicolor
    ##  [85] versicolor versicolor versicolor versicolor versicolor versicolor
    ##  [91] versicolor versicolor versicolor versicolor versicolor versicolor
    ##  [97] versicolor versicolor versicolor versicolor virginica  virginica 
    ## [103] virginica  virginica  virginica  virginica  virginica  virginica 
    ## [109] virginica  virginica  virginica  virginica  virginica  virginica 
    ## [115] virginica  virginica  virginica  virginica  virginica  virginica 
    ## [121] virginica  virginica  virginica  virginica  virginica  virginica 
    ## [127] virginica  virginica  virginica  virginica  virginica  virginica 
    ## [133] virginica  virginica  virginica  virginica  virginica  virginica 
    ## [139] virginica  virginica  virginica  virginica  virginica  virginica 
    ## [145] virginica  virginica  virginica  virginica  virginica  virginica 
    ## Levels: setosa versicolor virginica

We can store a variable as a new object and do stuff with it, e.g.:

    iris_pl<-iris$Petal.Length

    mean(iris_pl)

    ## [1] 3.758

Or if we don’t want to create an additional object we can use functions
‘on-the-fly’ to only display the value in the console.

    mean(iris$Petal.Length)

    ## [1] 3.758

    summary(iris$Petal.Length)

    ##    Min. 1st Qu.  Median    Mean 3rd Qu.    Max. 
    ##   1.000   1.600   4.350   3.758   5.100   6.900

### Positional Indices

Just as we did with vectors, we also can access data in data frames
using the square bracket \[ \] notation. However, instead of just using
a single index, we now need to use two indexes, one to specify the rows
and one for the columns. To do this, we can use the notation
my\_data\[rows, columns\] where rows and columns are indexes and
my\_data is the name of the data frame. Again, just like with our
vectors our indexes can be positional or the result of a logical test.

To use positional indexes we simple have to write the position of the
rows and columns we want to extract inside the \[ \]. For example, if
for some reason we wanted to extract the first value (1st row ) of the
height variable (4th column)

    iris[1, 3]

    ## [1] 1.4

    # this would give you the same
    iris$Petal.Length[1]

    ## [1] 1.4

We can also extract values from multiple rows or columns by specifying
these indexes as vectors inside the \[ \]. To extract the first 5 rows
and the first 3 columns we simple supply a vector containing a sequence
from 1 to 5 for the rows index (1:5) and a vector from 1 to 3 for the
column index (1:3).

    iris[1:5, 1:3]

    ##   Sepal.Length Sepal.Width Petal.Length
    ## 1          5.1         3.5          1.4
    ## 2          4.9         3.0          1.4
    ## 3          4.7         3.2          1.3
    ## 4          4.6         3.1          1.5
    ## 5          5.0         3.6          1.4

Or for non sequential rows and columns then we can supply vectors of
positions using the c() function. To extract the 1st, 5th, 12th, 30th
rows from the 1st, 3rd, and 5th columns

    iris[c(1, 5, 12, 30), c(1, 3, 5)]

    ##    Sepal.Length Petal.Length Species
    ## 1           5.1          1.4  setosa
    ## 5           5.0          1.4  setosa
    ## 12          4.8          1.6  setosa
    ## 30          4.7          1.6  setosa

All we are doing in the two examples above is creating vectors of
positions for the rows and columns that we want to extract. We have done
this by using the skills we developed when we generated vectors using
the c() function or using the : notation.

But what if we want to extract either all of the rows or all of the
columns? It would be extremely tedious to have to generate vectors for
all rows or for all columns. Thankfully R has a shortcut. If you don’t
specify either a row or column index in the \[ \] then R interprets it
to mean you want all rows or all columns. For example, to extract the
first 8 rows and all of the columns in the iris data frame:

    iris[1:8, ]

    ##   Sepal.Length Sepal.Width Petal.Length Petal.Width Species
    ## 1          5.1         3.5          1.4         0.2  setosa
    ## 2          4.9         3.0          1.4         0.2  setosa
    ## 3          4.7         3.2          1.3         0.2  setosa
    ## 4          4.6         3.1          1.5         0.2  setosa
    ## 5          5.0         3.6          1.4         0.2  setosa
    ## 6          5.4         3.9          1.7         0.4  setosa
    ## 7          4.6         3.4          1.4         0.3  setosa
    ## 8          5.0         3.4          1.5         0.2  setosa

or all of the rows and the first 3 columns. If you’re reading the web
version of this book scroll down in output panel to see all of the data.

    iris[, 1:3]

    ##     Sepal.Length Sepal.Width Petal.Length
    ## 1            5.1         3.5          1.4
    ## 2            4.9         3.0          1.4
    ## 3            4.7         3.2          1.3
    ## 4            4.6         3.1          1.5
    ## 5            5.0         3.6          1.4
    ## 6            5.4         3.9          1.7
    ## 7            4.6         3.4          1.4
    ## 8            5.0         3.4          1.5
    ## 9            4.4         2.9          1.4
    ## 10           4.9         3.1          1.5
    ## 11           5.4         3.7          1.5
    ## 12           4.8         3.4          1.6
    ## 13           4.8         3.0          1.4
    ## 14           4.3         3.0          1.1
    ## 15           5.8         4.0          1.2
    ## 16           5.7         4.4          1.5
    ## 17           5.4         3.9          1.3
    ## 18           5.1         3.5          1.4
    ## 19           5.7         3.8          1.7
    ## 20           5.1         3.8          1.5
    ## 21           5.4         3.4          1.7
    ## 22           5.1         3.7          1.5
    ## 23           4.6         3.6          1.0
    ## 24           5.1         3.3          1.7
    ## 25           4.8         3.4          1.9
    ## 26           5.0         3.0          1.6
    ## 27           5.0         3.4          1.6
    ## 28           5.2         3.5          1.5
    ## 29           5.2         3.4          1.4
    ## 30           4.7         3.2          1.6
    ## 31           4.8         3.1          1.6
    ## 32           5.4         3.4          1.5
    ## 33           5.2         4.1          1.5
    ## 34           5.5         4.2          1.4
    ## 35           4.9         3.1          1.5
    ## 36           5.0         3.2          1.2
    ## 37           5.5         3.5          1.3
    ## 38           4.9         3.6          1.4
    ## 39           4.4         3.0          1.3
    ## 40           5.1         3.4          1.5
    ## 41           5.0         3.5          1.3
    ## 42           4.5         2.3          1.3
    ## 43           4.4         3.2          1.3
    ## 44           5.0         3.5          1.6
    ## 45           5.1         3.8          1.9
    ## 46           4.8         3.0          1.4
    ## 47           5.1         3.8          1.6
    ## 48           4.6         3.2          1.4
    ## 49           5.3         3.7          1.5
    ## 50           5.0         3.3          1.4
    ## 51           7.0         3.2          4.7
    ## 52           6.4         3.2          4.5
    ## 53           6.9         3.1          4.9
    ## 54           5.5         2.3          4.0
    ## 55           6.5         2.8          4.6
    ## 56           5.7         2.8          4.5
    ## 57           6.3         3.3          4.7
    ## 58           4.9         2.4          3.3
    ## 59           6.6         2.9          4.6
    ## 60           5.2         2.7          3.9
    ## 61           5.0         2.0          3.5
    ## 62           5.9         3.0          4.2
    ## 63           6.0         2.2          4.0
    ## 64           6.1         2.9          4.7
    ## 65           5.6         2.9          3.6
    ## 66           6.7         3.1          4.4
    ## 67           5.6         3.0          4.5
    ## 68           5.8         2.7          4.1
    ## 69           6.2         2.2          4.5
    ## 70           5.6         2.5          3.9
    ## 71           5.9         3.2          4.8
    ## 72           6.1         2.8          4.0
    ## 73           6.3         2.5          4.9
    ## 74           6.1         2.8          4.7
    ## 75           6.4         2.9          4.3
    ## 76           6.6         3.0          4.4
    ## 77           6.8         2.8          4.8
    ## 78           6.7         3.0          5.0
    ## 79           6.0         2.9          4.5
    ## 80           5.7         2.6          3.5
    ## 81           5.5         2.4          3.8
    ## 82           5.5         2.4          3.7
    ## 83           5.8         2.7          3.9
    ## 84           6.0         2.7          5.1
    ## 85           5.4         3.0          4.5
    ## 86           6.0         3.4          4.5
    ## 87           6.7         3.1          4.7
    ## 88           6.3         2.3          4.4
    ## 89           5.6         3.0          4.1
    ## 90           5.5         2.5          4.0
    ## 91           5.5         2.6          4.4
    ## 92           6.1         3.0          4.6
    ## 93           5.8         2.6          4.0
    ## 94           5.0         2.3          3.3
    ## 95           5.6         2.7          4.2
    ## 96           5.7         3.0          4.2
    ## 97           5.7         2.9          4.2
    ## 98           6.2         2.9          4.3
    ## 99           5.1         2.5          3.0
    ## 100          5.7         2.8          4.1
    ## 101          6.3         3.3          6.0
    ## 102          5.8         2.7          5.1
    ## 103          7.1         3.0          5.9
    ## 104          6.3         2.9          5.6
    ## 105          6.5         3.0          5.8
    ## 106          7.6         3.0          6.6
    ## 107          4.9         2.5          4.5
    ## 108          7.3         2.9          6.3
    ## 109          6.7         2.5          5.8
    ## 110          7.2         3.6          6.1
    ## 111          6.5         3.2          5.1
    ## 112          6.4         2.7          5.3
    ## 113          6.8         3.0          5.5
    ## 114          5.7         2.5          5.0
    ## 115          5.8         2.8          5.1
    ## 116          6.4         3.2          5.3
    ## 117          6.5         3.0          5.5
    ## 118          7.7         3.8          6.7
    ## 119          7.7         2.6          6.9
    ## 120          6.0         2.2          5.0
    ## 121          6.9         3.2          5.7
    ## 122          5.6         2.8          4.9
    ## 123          7.7         2.8          6.7
    ## 124          6.3         2.7          4.9
    ## 125          6.7         3.3          5.7
    ## 126          7.2         3.2          6.0
    ## 127          6.2         2.8          4.8
    ## 128          6.1         3.0          4.9
    ## 129          6.4         2.8          5.6
    ## 130          7.2         3.0          5.8
    ## 131          7.4         2.8          6.1
    ## 132          7.9         3.8          6.4
    ## 133          6.4         2.8          5.6
    ## 134          6.3         2.8          5.1
    ## 135          6.1         2.6          5.6
    ## 136          7.7         3.0          6.1
    ## 137          6.3         3.4          5.6
    ## 138          6.4         3.1          5.5
    ## 139          6.0         3.0          4.8
    ## 140          6.9         3.1          5.4
    ## 141          6.7         3.1          5.6
    ## 142          6.9         3.1          5.1
    ## 143          5.8         2.7          5.1
    ## 144          6.8         3.2          5.9
    ## 145          6.7         3.3          5.7
    ## 146          6.7         3.0          5.2
    ## 147          6.3         2.5          5.0
    ## 148          6.5         3.0          5.2
    ## 149          6.2         3.4          5.4
    ## 150          5.9         3.0          5.1

We can even use negative positional indexes to exclude certain rows and
columns. As an example, lets extract all of the rows except the first 10
rows and all columns except the 2nd and 3rd. Notice we need to use -()
when we generate our row positional vectors. If we had just used -1:10
this would actually generate a regular sequence from -1 to 10 which is
not what we want (we can of course use -1:-10).

    iris[-(1:10), -c(2, 3)]

    ##     Sepal.Length Petal.Width    Species
    ## 11           5.4         0.2     setosa
    ## 12           4.8         0.2     setosa
    ## 13           4.8         0.1     setosa
    ## 14           4.3         0.1     setosa
    ## 15           5.8         0.2     setosa
    ## 16           5.7         0.4     setosa
    ## 17           5.4         0.4     setosa
    ## 18           5.1         0.3     setosa
    ## 19           5.7         0.3     setosa
    ## 20           5.1         0.3     setosa
    ## 21           5.4         0.2     setosa
    ## 22           5.1         0.4     setosa
    ## 23           4.6         0.2     setosa
    ## 24           5.1         0.5     setosa
    ## 25           4.8         0.2     setosa
    ## 26           5.0         0.2     setosa
    ## 27           5.0         0.4     setosa
    ## 28           5.2         0.2     setosa
    ## 29           5.2         0.2     setosa
    ## 30           4.7         0.2     setosa
    ## 31           4.8         0.2     setosa
    ## 32           5.4         0.4     setosa
    ## 33           5.2         0.1     setosa
    ## 34           5.5         0.2     setosa
    ## 35           4.9         0.2     setosa
    ## 36           5.0         0.2     setosa
    ## 37           5.5         0.2     setosa
    ## 38           4.9         0.1     setosa
    ## 39           4.4         0.2     setosa
    ## 40           5.1         0.2     setosa
    ## 41           5.0         0.3     setosa
    ## 42           4.5         0.3     setosa
    ## 43           4.4         0.2     setosa
    ## 44           5.0         0.6     setosa
    ## 45           5.1         0.4     setosa
    ## 46           4.8         0.3     setosa
    ## 47           5.1         0.2     setosa
    ## 48           4.6         0.2     setosa
    ## 49           5.3         0.2     setosa
    ## 50           5.0         0.2     setosa
    ## 51           7.0         1.4 versicolor
    ## 52           6.4         1.5 versicolor
    ## 53           6.9         1.5 versicolor
    ## 54           5.5         1.3 versicolor
    ## 55           6.5         1.5 versicolor
    ## 56           5.7         1.3 versicolor
    ## 57           6.3         1.6 versicolor
    ## 58           4.9         1.0 versicolor
    ## 59           6.6         1.3 versicolor
    ## 60           5.2         1.4 versicolor
    ## 61           5.0         1.0 versicolor
    ## 62           5.9         1.5 versicolor
    ## 63           6.0         1.0 versicolor
    ## 64           6.1         1.4 versicolor
    ## 65           5.6         1.3 versicolor
    ## 66           6.7         1.4 versicolor
    ## 67           5.6         1.5 versicolor
    ## 68           5.8         1.0 versicolor
    ## 69           6.2         1.5 versicolor
    ## 70           5.6         1.1 versicolor
    ## 71           5.9         1.8 versicolor
    ## 72           6.1         1.3 versicolor
    ## 73           6.3         1.5 versicolor
    ## 74           6.1         1.2 versicolor
    ## 75           6.4         1.3 versicolor
    ## 76           6.6         1.4 versicolor
    ## 77           6.8         1.4 versicolor
    ## 78           6.7         1.7 versicolor
    ## 79           6.0         1.5 versicolor
    ## 80           5.7         1.0 versicolor
    ## 81           5.5         1.1 versicolor
    ## 82           5.5         1.0 versicolor
    ## 83           5.8         1.2 versicolor
    ## 84           6.0         1.6 versicolor
    ## 85           5.4         1.5 versicolor
    ## 86           6.0         1.6 versicolor
    ## 87           6.7         1.5 versicolor
    ## 88           6.3         1.3 versicolor
    ## 89           5.6         1.3 versicolor
    ## 90           5.5         1.3 versicolor
    ## 91           5.5         1.2 versicolor
    ## 92           6.1         1.4 versicolor
    ## 93           5.8         1.2 versicolor
    ## 94           5.0         1.0 versicolor
    ## 95           5.6         1.3 versicolor
    ## 96           5.7         1.2 versicolor
    ## 97           5.7         1.3 versicolor
    ## 98           6.2         1.3 versicolor
    ## 99           5.1         1.1 versicolor
    ## 100          5.7         1.3 versicolor
    ## 101          6.3         2.5  virginica
    ## 102          5.8         1.9  virginica
    ## 103          7.1         2.1  virginica
    ## 104          6.3         1.8  virginica
    ## 105          6.5         2.2  virginica
    ## 106          7.6         2.1  virginica
    ## 107          4.9         1.7  virginica
    ## 108          7.3         1.8  virginica
    ## 109          6.7         1.8  virginica
    ## 110          7.2         2.5  virginica
    ## 111          6.5         2.0  virginica
    ## 112          6.4         1.9  virginica
    ## 113          6.8         2.1  virginica
    ## 114          5.7         2.0  virginica
    ## 115          5.8         2.4  virginica
    ## 116          6.4         2.3  virginica
    ## 117          6.5         1.8  virginica
    ## 118          7.7         2.2  virginica
    ## 119          7.7         2.3  virginica
    ## 120          6.0         1.5  virginica
    ## 121          6.9         2.3  virginica
    ## 122          5.6         2.0  virginica
    ## 123          7.7         2.0  virginica
    ## 124          6.3         1.8  virginica
    ## 125          6.7         2.1  virginica
    ## 126          7.2         1.8  virginica
    ## 127          6.2         1.8  virginica
    ## 128          6.1         1.8  virginica
    ## 129          6.4         2.1  virginica
    ## 130          7.2         1.6  virginica
    ## 131          7.4         1.9  virginica
    ## 132          7.9         2.0  virginica
    ## 133          6.4         2.2  virginica
    ## 134          6.3         1.5  virginica
    ## 135          6.1         1.4  virginica
    ## 136          7.7         2.3  virginica
    ## 137          6.3         2.4  virginica
    ## 138          6.4         1.8  virginica
    ## 139          6.0         1.8  virginica
    ## 140          6.9         2.1  virginica
    ## 141          6.7         2.4  virginica
    ## 142          6.9         2.3  virginica
    ## 143          5.8         1.9  virginica
    ## 144          6.8         2.3  virginica
    ## 145          6.7         2.5  virginica
    ## 146          6.7         2.3  virginica
    ## 147          6.3         1.9  virginica
    ## 148          6.5         2.0  virginica
    ## 149          6.2         2.3  virginica
    ## 150          5.9         1.8  virginica

In addition to using a positional index for extracting particular
columns (variables) we can also name the variables directly when using
the square bracket \[ \] notation.

    iris[1:5, c("Petal.Width", "Species")]

    ##   Petal.Width Species
    ## 1         0.2  setosa
    ## 2         0.2  setosa
    ## 3         0.2  setosa
    ## 4         0.2  setosa
    ## 5         0.2  setosa

We often use this method in preference to the positional index for
selecting columns as it will still give us what we want even if we’ve
changed the order of the columns in our data frame for some reason.

### Logical Indices

Just as we did with vectors, we can also extract data from our data
frame based on a logical test. We can use all of the logical operators
that we used for our vector examples. Let’s extract all rows where petal
width is greater than 0.5 and extract all columns by default (remember,
if you don’t include a column index after the comma it means all
columns).

    wide_petals <- iris[iris$Petal.Width > 0.5, ]

Notice in the code above that we need to use the iris$Peta.Width
notation for the logical test. If we just named the Petal.Width variable
without the name of the data frame we would receive an error telling us
R couldn’t find the variable Petal.Width The reason for this is that the
Petal.Width variable only exists inside the iris data frame so you need
to tell R exactly where it is.

So how does this work? The logical test is iris$Peta.Width &gt; 0.5 and
R will only extract those rows that satisfy this logical condition. If
we look at the output of just the logical condition you can see this
returns a vector containing TRUE if Petal.Width is greater than 0.5 and
FALSE if height is not greater than 0.5

    iris$Petal.Width > 0.5

    ##   [1] FALSE FALSE FALSE FALSE FALSE FALSE FALSE FALSE FALSE FALSE FALSE FALSE
    ##  [13] FALSE FALSE FALSE FALSE FALSE FALSE FALSE FALSE FALSE FALSE FALSE FALSE
    ##  [25] FALSE FALSE FALSE FALSE FALSE FALSE FALSE FALSE FALSE FALSE FALSE FALSE
    ##  [37] FALSE FALSE FALSE FALSE FALSE FALSE FALSE  TRUE FALSE FALSE FALSE FALSE
    ##  [49] FALSE FALSE  TRUE  TRUE  TRUE  TRUE  TRUE  TRUE  TRUE  TRUE  TRUE  TRUE
    ##  [61]  TRUE  TRUE  TRUE  TRUE  TRUE  TRUE  TRUE  TRUE  TRUE  TRUE  TRUE  TRUE
    ##  [73]  TRUE  TRUE  TRUE  TRUE  TRUE  TRUE  TRUE  TRUE  TRUE  TRUE  TRUE  TRUE
    ##  [85]  TRUE  TRUE  TRUE  TRUE  TRUE  TRUE  TRUE  TRUE  TRUE  TRUE  TRUE  TRUE
    ##  [97]  TRUE  TRUE  TRUE  TRUE  TRUE  TRUE  TRUE  TRUE  TRUE  TRUE  TRUE  TRUE
    ## [109]  TRUE  TRUE  TRUE  TRUE  TRUE  TRUE  TRUE  TRUE  TRUE  TRUE  TRUE  TRUE
    ## [121]  TRUE  TRUE  TRUE  TRUE  TRUE  TRUE  TRUE  TRUE  TRUE  TRUE  TRUE  TRUE
    ## [133]  TRUE  TRUE  TRUE  TRUE  TRUE  TRUE  TRUE  TRUE  TRUE  TRUE  TRUE  TRUE
    ## [145]  TRUE  TRUE  TRUE  TRUE  TRUE  TRUE

So our row index is a vector containing either TRUE or FALSE values and
only those rows that are TRUE are selected.

Other commonly used operators are shown below

    iris[iris$Petal.Width >= 0.5, ]        # values greater or equal to 0.5

    ##     Sepal.Length Sepal.Width Petal.Length Petal.Width    Species
    ## 24           5.1         3.3          1.7         0.5     setosa
    ## 44           5.0         3.5          1.6         0.6     setosa
    ## 51           7.0         3.2          4.7         1.4 versicolor
    ## 52           6.4         3.2          4.5         1.5 versicolor
    ## 53           6.9         3.1          4.9         1.5 versicolor
    ## 54           5.5         2.3          4.0         1.3 versicolor
    ## 55           6.5         2.8          4.6         1.5 versicolor
    ## 56           5.7         2.8          4.5         1.3 versicolor
    ## 57           6.3         3.3          4.7         1.6 versicolor
    ## 58           4.9         2.4          3.3         1.0 versicolor
    ## 59           6.6         2.9          4.6         1.3 versicolor
    ## 60           5.2         2.7          3.9         1.4 versicolor
    ## 61           5.0         2.0          3.5         1.0 versicolor
    ## 62           5.9         3.0          4.2         1.5 versicolor
    ## 63           6.0         2.2          4.0         1.0 versicolor
    ## 64           6.1         2.9          4.7         1.4 versicolor
    ## 65           5.6         2.9          3.6         1.3 versicolor
    ## 66           6.7         3.1          4.4         1.4 versicolor
    ## 67           5.6         3.0          4.5         1.5 versicolor
    ## 68           5.8         2.7          4.1         1.0 versicolor
    ## 69           6.2         2.2          4.5         1.5 versicolor
    ## 70           5.6         2.5          3.9         1.1 versicolor
    ## 71           5.9         3.2          4.8         1.8 versicolor
    ## 72           6.1         2.8          4.0         1.3 versicolor
    ## 73           6.3         2.5          4.9         1.5 versicolor
    ## 74           6.1         2.8          4.7         1.2 versicolor
    ## 75           6.4         2.9          4.3         1.3 versicolor
    ## 76           6.6         3.0          4.4         1.4 versicolor
    ## 77           6.8         2.8          4.8         1.4 versicolor
    ## 78           6.7         3.0          5.0         1.7 versicolor
    ## 79           6.0         2.9          4.5         1.5 versicolor
    ## 80           5.7         2.6          3.5         1.0 versicolor
    ## 81           5.5         2.4          3.8         1.1 versicolor
    ## 82           5.5         2.4          3.7         1.0 versicolor
    ## 83           5.8         2.7          3.9         1.2 versicolor
    ## 84           6.0         2.7          5.1         1.6 versicolor
    ## 85           5.4         3.0          4.5         1.5 versicolor
    ## 86           6.0         3.4          4.5         1.6 versicolor
    ## 87           6.7         3.1          4.7         1.5 versicolor
    ## 88           6.3         2.3          4.4         1.3 versicolor
    ## 89           5.6         3.0          4.1         1.3 versicolor
    ## 90           5.5         2.5          4.0         1.3 versicolor
    ## 91           5.5         2.6          4.4         1.2 versicolor
    ## 92           6.1         3.0          4.6         1.4 versicolor
    ## 93           5.8         2.6          4.0         1.2 versicolor
    ## 94           5.0         2.3          3.3         1.0 versicolor
    ## 95           5.6         2.7          4.2         1.3 versicolor
    ## 96           5.7         3.0          4.2         1.2 versicolor
    ## 97           5.7         2.9          4.2         1.3 versicolor
    ## 98           6.2         2.9          4.3         1.3 versicolor
    ## 99           5.1         2.5          3.0         1.1 versicolor
    ## 100          5.7         2.8          4.1         1.3 versicolor
    ## 101          6.3         3.3          6.0         2.5  virginica
    ## 102          5.8         2.7          5.1         1.9  virginica
    ## 103          7.1         3.0          5.9         2.1  virginica
    ## 104          6.3         2.9          5.6         1.8  virginica
    ## 105          6.5         3.0          5.8         2.2  virginica
    ## 106          7.6         3.0          6.6         2.1  virginica
    ## 107          4.9         2.5          4.5         1.7  virginica
    ## 108          7.3         2.9          6.3         1.8  virginica
    ## 109          6.7         2.5          5.8         1.8  virginica
    ## 110          7.2         3.6          6.1         2.5  virginica
    ## 111          6.5         3.2          5.1         2.0  virginica
    ## 112          6.4         2.7          5.3         1.9  virginica
    ## 113          6.8         3.0          5.5         2.1  virginica
    ## 114          5.7         2.5          5.0         2.0  virginica
    ## 115          5.8         2.8          5.1         2.4  virginica
    ## 116          6.4         3.2          5.3         2.3  virginica
    ## 117          6.5         3.0          5.5         1.8  virginica
    ## 118          7.7         3.8          6.7         2.2  virginica
    ## 119          7.7         2.6          6.9         2.3  virginica
    ## 120          6.0         2.2          5.0         1.5  virginica
    ## 121          6.9         3.2          5.7         2.3  virginica
    ## 122          5.6         2.8          4.9         2.0  virginica
    ## 123          7.7         2.8          6.7         2.0  virginica
    ## 124          6.3         2.7          4.9         1.8  virginica
    ## 125          6.7         3.3          5.7         2.1  virginica
    ## 126          7.2         3.2          6.0         1.8  virginica
    ## 127          6.2         2.8          4.8         1.8  virginica
    ## 128          6.1         3.0          4.9         1.8  virginica
    ## 129          6.4         2.8          5.6         2.1  virginica
    ## 130          7.2         3.0          5.8         1.6  virginica
    ## 131          7.4         2.8          6.1         1.9  virginica
    ## 132          7.9         3.8          6.4         2.0  virginica
    ## 133          6.4         2.8          5.6         2.2  virginica
    ## 134          6.3         2.8          5.1         1.5  virginica
    ## 135          6.1         2.6          5.6         1.4  virginica
    ## 136          7.7         3.0          6.1         2.3  virginica
    ## 137          6.3         3.4          5.6         2.4  virginica
    ## 138          6.4         3.1          5.5         1.8  virginica
    ## 139          6.0         3.0          4.8         1.8  virginica
    ## 140          6.9         3.1          5.4         2.1  virginica
    ## 141          6.7         3.1          5.6         2.4  virginica
    ## 142          6.9         3.1          5.1         2.3  virginica
    ## 143          5.8         2.7          5.1         1.9  virginica
    ## 144          6.8         3.2          5.9         2.3  virginica
    ## 145          6.7         3.3          5.7         2.5  virginica
    ## 146          6.7         3.0          5.2         2.3  virginica
    ## 147          6.3         2.5          5.0         1.9  virginica
    ## 148          6.5         3.0          5.2         2.0  virginica
    ## 149          6.2         3.4          5.4         2.3  virginica
    ## 150          5.9         3.0          5.1         1.8  virginica

    iris[iris$Petal.Width <= 0.5, ]          # values less than or equal to 0.5

    ##    Sepal.Length Sepal.Width Petal.Length Petal.Width Species
    ## 1           5.1         3.5          1.4         0.2  setosa
    ## 2           4.9         3.0          1.4         0.2  setosa
    ## 3           4.7         3.2          1.3         0.2  setosa
    ## 4           4.6         3.1          1.5         0.2  setosa
    ## 5           5.0         3.6          1.4         0.2  setosa
    ## 6           5.4         3.9          1.7         0.4  setosa
    ## 7           4.6         3.4          1.4         0.3  setosa
    ## 8           5.0         3.4          1.5         0.2  setosa
    ## 9           4.4         2.9          1.4         0.2  setosa
    ## 10          4.9         3.1          1.5         0.1  setosa
    ## 11          5.4         3.7          1.5         0.2  setosa
    ## 12          4.8         3.4          1.6         0.2  setosa
    ## 13          4.8         3.0          1.4         0.1  setosa
    ## 14          4.3         3.0          1.1         0.1  setosa
    ## 15          5.8         4.0          1.2         0.2  setosa
    ## 16          5.7         4.4          1.5         0.4  setosa
    ## 17          5.4         3.9          1.3         0.4  setosa
    ## 18          5.1         3.5          1.4         0.3  setosa
    ## 19          5.7         3.8          1.7         0.3  setosa
    ## 20          5.1         3.8          1.5         0.3  setosa
    ## 21          5.4         3.4          1.7         0.2  setosa
    ## 22          5.1         3.7          1.5         0.4  setosa
    ## 23          4.6         3.6          1.0         0.2  setosa
    ## 24          5.1         3.3          1.7         0.5  setosa
    ## 25          4.8         3.4          1.9         0.2  setosa
    ## 26          5.0         3.0          1.6         0.2  setosa
    ## 27          5.0         3.4          1.6         0.4  setosa
    ## 28          5.2         3.5          1.5         0.2  setosa
    ## 29          5.2         3.4          1.4         0.2  setosa
    ## 30          4.7         3.2          1.6         0.2  setosa
    ## 31          4.8         3.1          1.6         0.2  setosa
    ## 32          5.4         3.4          1.5         0.4  setosa
    ## 33          5.2         4.1          1.5         0.1  setosa
    ## 34          5.5         4.2          1.4         0.2  setosa
    ## 35          4.9         3.1          1.5         0.2  setosa
    ## 36          5.0         3.2          1.2         0.2  setosa
    ## 37          5.5         3.5          1.3         0.2  setosa
    ## 38          4.9         3.6          1.4         0.1  setosa
    ## 39          4.4         3.0          1.3         0.2  setosa
    ## 40          5.1         3.4          1.5         0.2  setosa
    ## 41          5.0         3.5          1.3         0.3  setosa
    ## 42          4.5         2.3          1.3         0.3  setosa
    ## 43          4.4         3.2          1.3         0.2  setosa
    ## 45          5.1         3.8          1.9         0.4  setosa
    ## 46          4.8         3.0          1.4         0.3  setosa
    ## 47          5.1         3.8          1.6         0.2  setosa
    ## 48          4.6         3.2          1.4         0.2  setosa
    ## 49          5.3         3.7          1.5         0.2  setosa
    ## 50          5.0         3.3          1.4         0.2  setosa

    iris[iris$Petal.Width == 0.5, ]          # values  equal to 0.5

    ##    Sepal.Length Sepal.Width Petal.Length Petal.Width Species
    ## 24          5.1         3.3          1.7         0.5  setosa

    iris[iris$Petal.Width != 0.5, ]          # values  not equal to 0.5

    ##     Sepal.Length Sepal.Width Petal.Length Petal.Width    Species
    ## 1            5.1         3.5          1.4         0.2     setosa
    ## 2            4.9         3.0          1.4         0.2     setosa
    ## 3            4.7         3.2          1.3         0.2     setosa
    ## 4            4.6         3.1          1.5         0.2     setosa
    ## 5            5.0         3.6          1.4         0.2     setosa
    ## 6            5.4         3.9          1.7         0.4     setosa
    ## 7            4.6         3.4          1.4         0.3     setosa
    ## 8            5.0         3.4          1.5         0.2     setosa
    ## 9            4.4         2.9          1.4         0.2     setosa
    ## 10           4.9         3.1          1.5         0.1     setosa
    ## 11           5.4         3.7          1.5         0.2     setosa
    ## 12           4.8         3.4          1.6         0.2     setosa
    ## 13           4.8         3.0          1.4         0.1     setosa
    ## 14           4.3         3.0          1.1         0.1     setosa
    ## 15           5.8         4.0          1.2         0.2     setosa
    ## 16           5.7         4.4          1.5         0.4     setosa
    ## 17           5.4         3.9          1.3         0.4     setosa
    ## 18           5.1         3.5          1.4         0.3     setosa
    ## 19           5.7         3.8          1.7         0.3     setosa
    ## 20           5.1         3.8          1.5         0.3     setosa
    ## 21           5.4         3.4          1.7         0.2     setosa
    ## 22           5.1         3.7          1.5         0.4     setosa
    ## 23           4.6         3.6          1.0         0.2     setosa
    ## 25           4.8         3.4          1.9         0.2     setosa
    ## 26           5.0         3.0          1.6         0.2     setosa
    ## 27           5.0         3.4          1.6         0.4     setosa
    ## 28           5.2         3.5          1.5         0.2     setosa
    ## 29           5.2         3.4          1.4         0.2     setosa
    ## 30           4.7         3.2          1.6         0.2     setosa
    ## 31           4.8         3.1          1.6         0.2     setosa
    ## 32           5.4         3.4          1.5         0.4     setosa
    ## 33           5.2         4.1          1.5         0.1     setosa
    ## 34           5.5         4.2          1.4         0.2     setosa
    ## 35           4.9         3.1          1.5         0.2     setosa
    ## 36           5.0         3.2          1.2         0.2     setosa
    ## 37           5.5         3.5          1.3         0.2     setosa
    ## 38           4.9         3.6          1.4         0.1     setosa
    ## 39           4.4         3.0          1.3         0.2     setosa
    ## 40           5.1         3.4          1.5         0.2     setosa
    ## 41           5.0         3.5          1.3         0.3     setosa
    ## 42           4.5         2.3          1.3         0.3     setosa
    ## 43           4.4         3.2          1.3         0.2     setosa
    ## 44           5.0         3.5          1.6         0.6     setosa
    ## 45           5.1         3.8          1.9         0.4     setosa
    ## 46           4.8         3.0          1.4         0.3     setosa
    ## 47           5.1         3.8          1.6         0.2     setosa
    ## 48           4.6         3.2          1.4         0.2     setosa
    ## 49           5.3         3.7          1.5         0.2     setosa
    ## 50           5.0         3.3          1.4         0.2     setosa
    ## 51           7.0         3.2          4.7         1.4 versicolor
    ## 52           6.4         3.2          4.5         1.5 versicolor
    ## 53           6.9         3.1          4.9         1.5 versicolor
    ## 54           5.5         2.3          4.0         1.3 versicolor
    ## 55           6.5         2.8          4.6         1.5 versicolor
    ## 56           5.7         2.8          4.5         1.3 versicolor
    ## 57           6.3         3.3          4.7         1.6 versicolor
    ## 58           4.9         2.4          3.3         1.0 versicolor
    ## 59           6.6         2.9          4.6         1.3 versicolor
    ## 60           5.2         2.7          3.9         1.4 versicolor
    ## 61           5.0         2.0          3.5         1.0 versicolor
    ## 62           5.9         3.0          4.2         1.5 versicolor
    ## 63           6.0         2.2          4.0         1.0 versicolor
    ## 64           6.1         2.9          4.7         1.4 versicolor
    ## 65           5.6         2.9          3.6         1.3 versicolor
    ## 66           6.7         3.1          4.4         1.4 versicolor
    ## 67           5.6         3.0          4.5         1.5 versicolor
    ## 68           5.8         2.7          4.1         1.0 versicolor
    ## 69           6.2         2.2          4.5         1.5 versicolor
    ## 70           5.6         2.5          3.9         1.1 versicolor
    ## 71           5.9         3.2          4.8         1.8 versicolor
    ## 72           6.1         2.8          4.0         1.3 versicolor
    ## 73           6.3         2.5          4.9         1.5 versicolor
    ## 74           6.1         2.8          4.7         1.2 versicolor
    ## 75           6.4         2.9          4.3         1.3 versicolor
    ## 76           6.6         3.0          4.4         1.4 versicolor
    ## 77           6.8         2.8          4.8         1.4 versicolor
    ## 78           6.7         3.0          5.0         1.7 versicolor
    ## 79           6.0         2.9          4.5         1.5 versicolor
    ## 80           5.7         2.6          3.5         1.0 versicolor
    ## 81           5.5         2.4          3.8         1.1 versicolor
    ## 82           5.5         2.4          3.7         1.0 versicolor
    ## 83           5.8         2.7          3.9         1.2 versicolor
    ## 84           6.0         2.7          5.1         1.6 versicolor
    ## 85           5.4         3.0          4.5         1.5 versicolor
    ## 86           6.0         3.4          4.5         1.6 versicolor
    ## 87           6.7         3.1          4.7         1.5 versicolor
    ## 88           6.3         2.3          4.4         1.3 versicolor
    ## 89           5.6         3.0          4.1         1.3 versicolor
    ## 90           5.5         2.5          4.0         1.3 versicolor
    ## 91           5.5         2.6          4.4         1.2 versicolor
    ## 92           6.1         3.0          4.6         1.4 versicolor
    ## 93           5.8         2.6          4.0         1.2 versicolor
    ## 94           5.0         2.3          3.3         1.0 versicolor
    ## 95           5.6         2.7          4.2         1.3 versicolor
    ## 96           5.7         3.0          4.2         1.2 versicolor
    ## 97           5.7         2.9          4.2         1.3 versicolor
    ## 98           6.2         2.9          4.3         1.3 versicolor
    ## 99           5.1         2.5          3.0         1.1 versicolor
    ## 100          5.7         2.8          4.1         1.3 versicolor
    ## 101          6.3         3.3          6.0         2.5  virginica
    ## 102          5.8         2.7          5.1         1.9  virginica
    ## 103          7.1         3.0          5.9         2.1  virginica
    ## 104          6.3         2.9          5.6         1.8  virginica
    ## 105          6.5         3.0          5.8         2.2  virginica
    ## 106          7.6         3.0          6.6         2.1  virginica
    ## 107          4.9         2.5          4.5         1.7  virginica
    ## 108          7.3         2.9          6.3         1.8  virginica
    ## 109          6.7         2.5          5.8         1.8  virginica
    ## 110          7.2         3.6          6.1         2.5  virginica
    ## 111          6.5         3.2          5.1         2.0  virginica
    ## 112          6.4         2.7          5.3         1.9  virginica
    ## 113          6.8         3.0          5.5         2.1  virginica
    ## 114          5.7         2.5          5.0         2.0  virginica
    ## 115          5.8         2.8          5.1         2.4  virginica
    ## 116          6.4         3.2          5.3         2.3  virginica
    ## 117          6.5         3.0          5.5         1.8  virginica
    ## 118          7.7         3.8          6.7         2.2  virginica
    ## 119          7.7         2.6          6.9         2.3  virginica
    ## 120          6.0         2.2          5.0         1.5  virginica
    ## 121          6.9         3.2          5.7         2.3  virginica
    ## 122          5.6         2.8          4.9         2.0  virginica
    ## 123          7.7         2.8          6.7         2.0  virginica
    ## 124          6.3         2.7          4.9         1.8  virginica
    ## 125          6.7         3.3          5.7         2.1  virginica
    ## 126          7.2         3.2          6.0         1.8  virginica
    ## 127          6.2         2.8          4.8         1.8  virginica
    ## 128          6.1         3.0          4.9         1.8  virginica
    ## 129          6.4         2.8          5.6         2.1  virginica
    ## 130          7.2         3.0          5.8         1.6  virginica
    ## 131          7.4         2.8          6.1         1.9  virginica
    ## 132          7.9         3.8          6.4         2.0  virginica
    ## 133          6.4         2.8          5.6         2.2  virginica
    ## 134          6.3         2.8          5.1         1.5  virginica
    ## 135          6.1         2.6          5.6         1.4  virginica
    ## 136          7.7         3.0          6.1         2.3  virginica
    ## 137          6.3         3.4          5.6         2.4  virginica
    ## 138          6.4         3.1          5.5         1.8  virginica
    ## 139          6.0         3.0          4.8         1.8  virginica
    ## 140          6.9         3.1          5.4         2.1  virginica
    ## 141          6.7         3.1          5.6         2.4  virginica
    ## 142          6.9         3.1          5.1         2.3  virginica
    ## 143          5.8         2.7          5.1         1.9  virginica
    ## 144          6.8         3.2          5.9         2.3  virginica
    ## 145          6.7         3.3          5.7         2.5  virginica
    ## 146          6.7         3.0          5.2         2.3  virginica
    ## 147          6.3         2.5          5.0         1.9  virginica
    ## 148          6.5         3.0          5.2         2.0  virginica
    ## 149          6.2         3.4          5.4         2.3  virginica
    ## 150          5.9         3.0          5.1         1.8  virginica

We can also extract rows based on the value of a character string or
factor level. Let’s extract all rows where the species level is equal to
setosa (again we will output all columns). Notice that the double equals
== sign must be used for a logical test and that the character string
must be enclosed in either single or double quotes (i.e. “setosa”).

    iris_setosas <- iris[iris$Species == "setosa", ]        
    iris_setosas

    ##    Sepal.Length Sepal.Width Petal.Length Petal.Width Species
    ## 1           5.1         3.5          1.4         0.2  setosa
    ## 2           4.9         3.0          1.4         0.2  setosa
    ## 3           4.7         3.2          1.3         0.2  setosa
    ## 4           4.6         3.1          1.5         0.2  setosa
    ## 5           5.0         3.6          1.4         0.2  setosa
    ## 6           5.4         3.9          1.7         0.4  setosa
    ## 7           4.6         3.4          1.4         0.3  setosa
    ## 8           5.0         3.4          1.5         0.2  setosa
    ## 9           4.4         2.9          1.4         0.2  setosa
    ## 10          4.9         3.1          1.5         0.1  setosa
    ## 11          5.4         3.7          1.5         0.2  setosa
    ## 12          4.8         3.4          1.6         0.2  setosa
    ## 13          4.8         3.0          1.4         0.1  setosa
    ## 14          4.3         3.0          1.1         0.1  setosa
    ## 15          5.8         4.0          1.2         0.2  setosa
    ## 16          5.7         4.4          1.5         0.4  setosa
    ## 17          5.4         3.9          1.3         0.4  setosa
    ## 18          5.1         3.5          1.4         0.3  setosa
    ## 19          5.7         3.8          1.7         0.3  setosa
    ## 20          5.1         3.8          1.5         0.3  setosa
    ## 21          5.4         3.4          1.7         0.2  setosa
    ## 22          5.1         3.7          1.5         0.4  setosa
    ## 23          4.6         3.6          1.0         0.2  setosa
    ## 24          5.1         3.3          1.7         0.5  setosa
    ## 25          4.8         3.4          1.9         0.2  setosa
    ## 26          5.0         3.0          1.6         0.2  setosa
    ## 27          5.0         3.4          1.6         0.4  setosa
    ## 28          5.2         3.5          1.5         0.2  setosa
    ## 29          5.2         3.4          1.4         0.2  setosa
    ## 30          4.7         3.2          1.6         0.2  setosa
    ## 31          4.8         3.1          1.6         0.2  setosa
    ## 32          5.4         3.4          1.5         0.4  setosa
    ## 33          5.2         4.1          1.5         0.1  setosa
    ## 34          5.5         4.2          1.4         0.2  setosa
    ## 35          4.9         3.1          1.5         0.2  setosa
    ## 36          5.0         3.2          1.2         0.2  setosa
    ## 37          5.5         3.5          1.3         0.2  setosa
    ## 38          4.9         3.6          1.4         0.1  setosa
    ## 39          4.4         3.0          1.3         0.2  setosa
    ## 40          5.1         3.4          1.5         0.2  setosa
    ## 41          5.0         3.5          1.3         0.3  setosa
    ## 42          4.5         2.3          1.3         0.3  setosa
    ## 43          4.4         3.2          1.3         0.2  setosa
    ## 44          5.0         3.5          1.6         0.6  setosa
    ## 45          5.1         3.8          1.9         0.4  setosa
    ## 46          4.8         3.0          1.4         0.3  setosa
    ## 47          5.1         3.8          1.6         0.2  setosa
    ## 48          4.6         3.2          1.4         0.2  setosa
    ## 49          5.3         3.7          1.5         0.2  setosa
    ## 50          5.0         3.3          1.4         0.2  setosa

Or we can extract all rows where species is not equal to setosa (using
!=):

    iris_others <- iris[iris$Species != "setosa", ]        
    iris_others

    ##     Sepal.Length Sepal.Width Petal.Length Petal.Width    Species
    ## 51           7.0         3.2          4.7         1.4 versicolor
    ## 52           6.4         3.2          4.5         1.5 versicolor
    ## 53           6.9         3.1          4.9         1.5 versicolor
    ## 54           5.5         2.3          4.0         1.3 versicolor
    ## 55           6.5         2.8          4.6         1.5 versicolor
    ## 56           5.7         2.8          4.5         1.3 versicolor
    ## 57           6.3         3.3          4.7         1.6 versicolor
    ## 58           4.9         2.4          3.3         1.0 versicolor
    ## 59           6.6         2.9          4.6         1.3 versicolor
    ## 60           5.2         2.7          3.9         1.4 versicolor
    ## 61           5.0         2.0          3.5         1.0 versicolor
    ## 62           5.9         3.0          4.2         1.5 versicolor
    ## 63           6.0         2.2          4.0         1.0 versicolor
    ## 64           6.1         2.9          4.7         1.4 versicolor
    ## 65           5.6         2.9          3.6         1.3 versicolor
    ## 66           6.7         3.1          4.4         1.4 versicolor
    ## 67           5.6         3.0          4.5         1.5 versicolor
    ## 68           5.8         2.7          4.1         1.0 versicolor
    ## 69           6.2         2.2          4.5         1.5 versicolor
    ## 70           5.6         2.5          3.9         1.1 versicolor
    ## 71           5.9         3.2          4.8         1.8 versicolor
    ## 72           6.1         2.8          4.0         1.3 versicolor
    ## 73           6.3         2.5          4.9         1.5 versicolor
    ## 74           6.1         2.8          4.7         1.2 versicolor
    ## 75           6.4         2.9          4.3         1.3 versicolor
    ## 76           6.6         3.0          4.4         1.4 versicolor
    ## 77           6.8         2.8          4.8         1.4 versicolor
    ## 78           6.7         3.0          5.0         1.7 versicolor
    ## 79           6.0         2.9          4.5         1.5 versicolor
    ## 80           5.7         2.6          3.5         1.0 versicolor
    ## 81           5.5         2.4          3.8         1.1 versicolor
    ## 82           5.5         2.4          3.7         1.0 versicolor
    ## 83           5.8         2.7          3.9         1.2 versicolor
    ## 84           6.0         2.7          5.1         1.6 versicolor
    ## 85           5.4         3.0          4.5         1.5 versicolor
    ## 86           6.0         3.4          4.5         1.6 versicolor
    ## 87           6.7         3.1          4.7         1.5 versicolor
    ## 88           6.3         2.3          4.4         1.3 versicolor
    ## 89           5.6         3.0          4.1         1.3 versicolor
    ## 90           5.5         2.5          4.0         1.3 versicolor
    ## 91           5.5         2.6          4.4         1.2 versicolor
    ## 92           6.1         3.0          4.6         1.4 versicolor
    ## 93           5.8         2.6          4.0         1.2 versicolor
    ## 94           5.0         2.3          3.3         1.0 versicolor
    ## 95           5.6         2.7          4.2         1.3 versicolor
    ## 96           5.7         3.0          4.2         1.2 versicolor
    ## 97           5.7         2.9          4.2         1.3 versicolor
    ## 98           6.2         2.9          4.3         1.3 versicolor
    ## 99           5.1         2.5          3.0         1.1 versicolor
    ## 100          5.7         2.8          4.1         1.3 versicolor
    ## 101          6.3         3.3          6.0         2.5  virginica
    ## 102          5.8         2.7          5.1         1.9  virginica
    ## 103          7.1         3.0          5.9         2.1  virginica
    ## 104          6.3         2.9          5.6         1.8  virginica
    ## 105          6.5         3.0          5.8         2.2  virginica
    ## 106          7.6         3.0          6.6         2.1  virginica
    ## 107          4.9         2.5          4.5         1.7  virginica
    ## 108          7.3         2.9          6.3         1.8  virginica
    ## 109          6.7         2.5          5.8         1.8  virginica
    ## 110          7.2         3.6          6.1         2.5  virginica
    ## 111          6.5         3.2          5.1         2.0  virginica
    ## 112          6.4         2.7          5.3         1.9  virginica
    ## 113          6.8         3.0          5.5         2.1  virginica
    ## 114          5.7         2.5          5.0         2.0  virginica
    ## 115          5.8         2.8          5.1         2.4  virginica
    ## 116          6.4         3.2          5.3         2.3  virginica
    ## 117          6.5         3.0          5.5         1.8  virginica
    ## 118          7.7         3.8          6.7         2.2  virginica
    ## 119          7.7         2.6          6.9         2.3  virginica
    ## 120          6.0         2.2          5.0         1.5  virginica
    ## 121          6.9         3.2          5.7         2.3  virginica
    ## 122          5.6         2.8          4.9         2.0  virginica
    ## 123          7.7         2.8          6.7         2.0  virginica
    ## 124          6.3         2.7          4.9         1.8  virginica
    ## 125          6.7         3.3          5.7         2.1  virginica
    ## 126          7.2         3.2          6.0         1.8  virginica
    ## 127          6.2         2.8          4.8         1.8  virginica
    ## 128          6.1         3.0          4.9         1.8  virginica
    ## 129          6.4         2.8          5.6         2.1  virginica
    ## 130          7.2         3.0          5.8         1.6  virginica
    ## 131          7.4         2.8          6.1         1.9  virginica
    ## 132          7.9         3.8          6.4         2.0  virginica
    ## 133          6.4         2.8          5.6         2.2  virginica
    ## 134          6.3         2.8          5.1         1.5  virginica
    ## 135          6.1         2.6          5.6         1.4  virginica
    ## 136          7.7         3.0          6.1         2.3  virginica
    ## 137          6.3         3.4          5.6         2.4  virginica
    ## 138          6.4         3.1          5.5         1.8  virginica
    ## 139          6.0         3.0          4.8         1.8  virginica
    ## 140          6.9         3.1          5.4         2.1  virginica
    ## 141          6.7         3.1          5.6         2.4  virginica
    ## 142          6.9         3.1          5.1         2.3  virginica
    ## 143          5.8         2.7          5.1         1.9  virginica
    ## 144          6.8         3.2          5.9         2.3  virginica
    ## 145          6.7         3.3          5.7         2.5  virginica
    ## 146          6.7         3.0          5.2         2.3  virginica
    ## 147          6.3         2.5          5.0         1.9  virginica
    ## 148          6.5         3.0          5.2         2.0  virginica
    ## 149          6.2         3.4          5.4         2.3  virginica
    ## 150          5.9         3.0          5.1         1.8  virginica

We can increase the complexity of our logical tests by combining them
with Boolean expressions just as we did for vector objects. For example,
to extract all rows where Petal.Width is greater or equal to 0.5 AND
species is equal to ‘virginica’ AND Petal.Length is less than 5.3, we
combine a series of logical expressions with the & symbol.

    iris[iris$Petal.Width>=0.5 & iris$Species=="virginica" & iris$Petal.Length<5.3, ]

    ##     Sepal.Length Sepal.Width Petal.Length Petal.Width   Species
    ## 102          5.8         2.7          5.1         1.9 virginica
    ## 107          4.9         2.5          4.5         1.7 virginica
    ## 111          6.5         3.2          5.1         2.0 virginica
    ## 114          5.7         2.5          5.0         2.0 virginica
    ## 115          5.8         2.8          5.1         2.4 virginica
    ## 120          6.0         2.2          5.0         1.5 virginica
    ## 122          5.6         2.8          4.9         2.0 virginica
    ## 124          6.3         2.7          4.9         1.8 virginica
    ## 127          6.2         2.8          4.8         1.8 virginica
    ## 128          6.1         3.0          4.9         1.8 virginica
    ## 134          6.3         2.8          5.1         1.5 virginica
    ## 139          6.0         3.0          4.8         1.8 virginica
    ## 142          6.9         3.1          5.1         2.3 virginica
    ## 143          5.8         2.7          5.1         1.9 virginica
    ## 146          6.7         3.0          5.2         2.3 virginica
    ## 147          6.3         2.5          5.0         1.9 virginica
    ## 148          6.5         3.0          5.2         2.0 virginica
    ## 150          5.9         3.0          5.1         1.8 virginica

To extract rows based on an ‘OR’ Boolean expression we can use the |
symbol. Let’s extract all rows where Petal.Length is greater than 6 OR
less than 1.3:

    iris[iris$Petal.Length>6 | iris$Petal.Length<1.3, ]

    ##     Sepal.Length Sepal.Width Petal.Length Petal.Width   Species
    ## 14           4.3         3.0          1.1         0.1    setosa
    ## 15           5.8         4.0          1.2         0.2    setosa
    ## 23           4.6         3.6          1.0         0.2    setosa
    ## 36           5.0         3.2          1.2         0.2    setosa
    ## 106          7.6         3.0          6.6         2.1 virginica
    ## 108          7.3         2.9          6.3         1.8 virginica
    ## 110          7.2         3.6          6.1         2.5 virginica
    ## 118          7.7         3.8          6.7         2.2 virginica
    ## 119          7.7         2.6          6.9         2.3 virginica
    ## 123          7.7         2.8          6.7         2.0 virginica
    ## 131          7.4         2.8          6.1         1.9 virginica
    ## 132          7.9         3.8          6.4         2.0 virginica
    ## 136          7.7         3.0          6.1         2.3 virginica

An alternative method of selecting parts of a data frame based on a
logical expression is to use the subset() function instead of the \[ \].
The advantage of using subset() is that you no longer need to use the $
notation when specifying variables inside the data frame as the first
argument to the function is the name of the data frame to be subsetted.
The disadvantage is that subset() is less flexible than the \[ \]
notation.

    my_subset<-subset(iris, Species == "setosa" & Petal.Length == 1.2)
    my_subset

    ##    Sepal.Length Sepal.Width Petal.Length Petal.Width Species
    ## 15          5.8         4.0          1.2         0.2  setosa
    ## 36          5.0         3.2          1.2         0.2  setosa

And if you only want certain columns you can use the select = argument.

    my_subset<-subset(iris, Species == "setosa" & Petal.Length == 1.2,
                      select=c("Sepal.Length", "Sepal.Width"))
    my_subset

    ##    Sepal.Length Sepal.Width
    ## 15          5.8         4.0
    ## 36          5.0         3.2

You can order dataframes just like the vectors we discussed above; we
will skip this for now, but see the [full
tutorial](https://intro2r.com/wrangling-data-frames.html#ordering-data-frames)
for a complete treatment of this topic.

### Adding columns and rows

Sometimes it’s useful to be able to add extra rows and columns of data
to our data frames. There are multiple ways to achieve this (as there
always is in R!) depending on your circumstances. To simply append
additional rows to an existing data frame we can use the rbind()
function and to append columns the cbind() function. Let’s create a
couple of test data frames to see this in action using our old friend
the data.frame() function.

    # rbind for rows
    df1 <- data.frame(id = 1:4, height = c(120, 150, 132, 122),
                            weight = c(44, 56, 49, 45))
    df1

    ##   id height weight
    ## 1  1    120     44
    ## 2  2    150     56
    ## 3  3    132     49
    ## 4  4    122     45

    df2 <- data.frame(id = 5:6, height = c(119, 110),
                            weight = c(39, 35))
    df2

    ##   id height weight
    ## 1  5    119     39
    ## 2  6    110     35

    df3 <- data.frame(id = 1:4, height = c(120, 150, 132, 122),
                            weight = c(44, 56, 49, 45))
    df3

    ##   id height weight
    ## 1  1    120     44
    ## 2  2    150     56
    ## 3  3    132     49
    ## 4  4    122     45

    df4 <- data.frame(location = c("UK", "CZ", "CZ", "UK"))
    df4

    ##   location
    ## 1       UK
    ## 2       CZ
    ## 3       CZ
    ## 4       UK

We can use the rbind() function to append the rows of data in df2 to the
rows in df1 and assign the new data frame to df\_rcomb.

    df_rcomb <- rbind(df1, df2)
    df_rcomb

    ##   id height weight
    ## 1  1    120     44
    ## 2  2    150     56
    ## 3  3    132     49
    ## 4  4    122     45
    ## 5  5    119     39
    ## 6  6    110     35

And cbind to append the column in df4 to the df3 data frame and assign
to df\_ccomb\`.

    df_ccomb <- cbind(df3, df4)
    df_ccomb

    ##   id height weight location
    ## 1  1    120     44       UK
    ## 2  2    150     56       CZ
    ## 3  3    132     49       CZ
    ## 4  4    122     45       UK

Another situation when adding a new column to a data frame is useful is
when you want to perform some kind of transformation on an existing
variable. For example, say we wanted to apply a log10 transformation on
the height variable in the df\_rcomb data frame we created above. We
could just create a separate variable to contains these values but it’s
good practice to create this variable as a new column inside our
existing data frame so we keep all of our data together. Let’s call this
new variable height\_log10.

    df_rcomb$height_log10 <- log10(df_rcomb$height)
    df_rcomb

    ##   id height weight height_log10
    ## 1  1    120     44     2.079181
    ## 2  2    150     56     2.176091
    ## 3  3    132     49     2.120574
    ## 4  4    122     45     2.086360
    ## 5  5    119     39     2.075547
    ## 6  6    110     35     2.041393

This situation also crops up when we want to convert an existing
variable in a data frame from one data class to another data class. For
example, the id variable in the df\_rcomb data frame is numeric type
data (use the str() or class() functions to check for yourself). If we
wanted to convert the id variable to a factor to use later in our
analysis we can create a new variable called Fid in our data frame and
use the factor() function to convert the id variable.

    df_rcomb$Fid <- factor(df_rcomb$id)
    df_rcomb

    ##   id height weight height_log10 Fid
    ## 1  1    120     44     2.079181   1
    ## 2  2    150     56     2.176091   2
    ## 3  3    132     49     2.120574   3
    ## 4  4    122     45     2.086360   4
    ## 5  5    119     39     2.075547   5
    ## 6  6    110     35     2.041393   6

    str(df_rcomb)

    ## 'data.frame':    6 obs. of  5 variables:
    ##  $ id          : int  1 2 3 4 5 6
    ##  $ height      : num  120 150 132 122 119 110
    ##  $ weight      : num  44 56 49 45 39 35
    ##  $ height_log10: num  2.08 2.18 2.12 2.09 2.08 ...
    ##  $ Fid         : Factor w/ 6 levels "1","2","3","4",..: 1 2 3 4 5 6

There is also lots to say about
[merging](https://intro2r.com/wrangling-data-frames.html#merging-data-frames),
[reshaping](https://intro2r.com/wrangling-data-frames.html#reshape), and
[summarizing](https://intro2r.com/summarising-data-frames.html)
dataframes for different purposes. Again, for a great explanation, see
the relevant sections of the tutorial.

## Plotting in R

The most common high level function used to produce plots in R is
(rather unsurprisingly) the plot() function. For example, let’s plot
petal widths of iris plants from our irs data frame.

    plot(iris$Petal.Width)

![](Intro2R_files/figure-markdown_strict/plot1-1.png)

R has plotted the values of Petal.Width (on the y axis) against an index
since we are only plotting one variable to plot. The index is just the
order of the weight values in the data frame (1 first in the data frame
and 150 last). The weight variable name has been automatically included
as a y axis label and the axes scales have been automatically set.

To plot a scatterplot of one numeric variable against another numeric
variable we just need to include both variables as arguments when using
the plot() function. For example to plot Petal.Width on the y axis and
Petal.Length on the x axis:

    plot(y=iris$Petal.Width, x=iris$Petal.Length)

![](Intro2R_files/figure-markdown_strict/plot2-1.png)

There is an equivalent approach for these types of plots which often
causes some confusion at first. You can also use the formula notation
when using the plot() function. However, in contrast to the previous
method the formula method requires you to specify the y axis variable
first, then a ~ and then our x axis variable.

    plot(iris$Petal.Width~iris$Petal.Length)

![](Intro2R_files/figure-markdown_strict/plot3-1.png)

Both of these two approaches are equivalent so we suggest that you just
choose the one you prefer and go with it.

You can also specify the type of graph you wish to plot using the
argument type =. You can plot just the points (type = “p”, this is the
default), just lines (type = “l”), both points and lines connected (type
= “b”), both points and lines with the lines running through the points
(type = “o”) and empty points joined by lines (type = “c”).

    plot(iris$Petal.Width~iris$Petal.Length, type="l")

![](Intro2R_files/figure-markdown_strict/plot4-1.png)

    plot(iris$Petal.Width~iris$Petal.Length, type="b")

![](Intro2R_files/figure-markdown_strict/plot4-2.png)

    plot(iris$Petal.Width~iris$Petal.Length, type="c")

![](Intro2R_files/figure-markdown_strict/plot4-3.png)

The plots we’ve produced so far don’t look anything particularly
special. However, the plot() function is incredibly versatile and can
generate a large range of plots which you can customise to your own
taste. We’ll cover how to customize plots later. As a quick aside, the
plot() function is also what’s known as a generic function which means
it can change its default behaviour depending on the type of object used
as an argument.

There are lots of types of plots you can make in R. We’ll show two more
examples here.

Frequency histograms are useful when you want to get an idea about the
distribution of values in a numeric variable. The hist() function takes
a numeric vector as its main argument. Let’s generate a histogram of the
Petal.Width values.

    hist(iris$Petal.Width)

![](Intro2R_files/figure-markdown_strict/plot5-1.png)

The hist() function automatically creates the breakpoints (or bins) in
the histogram using the Sturges formula unless you specify otherwise by
using the break = argument. For example, let’s say we want to plot our
histogram with breakpoints every 0.5 cm. We first generate a sequence
from zero to the maximum value (2.5), in steps of 1, using the seq()
function. We can then use this sequence with the breaks = argument.
While we’re at it, let’s also replace the title for something a little
better using the main = argument

    max_val<-max(iris$Petal.Width)

    brk <- seq(from = 0, to = max_val, by = 0.5)

    hist(iris$Petal.Width, breaks = brk, main = "Iris Petal Widths")

![](Intro2R_files/figure-markdown_strict/plot6-1.png)

Boxplots are another way to explore data, and to see its distribution.

To create a boxplot in R we use the boxplot() function. For example,
let’s create a boxplot of the variable Petal.Length from our iris data
frame. We can also include a y axis label using the ylab = argument.

    boxplot(iris$Petal.Length, ylab = "Petal Length (cm)")

![](Intro2R_files/figure-markdown_strict/plot7-1.png)

The thick horizontal line in the middle of the box is the median value
of weight (around 11 g). The upper line of the box is the upper quartile
(75th percentile) and the lower line is the lower quartile (25th
percentile). The distance between the upper and lower quartiles is known
as the inter quartile range and represents the values of weight for 50%
of the data. The dotted vertical lines are called the whiskers and their
length is determined as 1.5 x the inter quartile range. Data points that
are plotted outside the the whiskers represent potential unusual
observations. This doesn’t mean they are unusual, just that they warrant
a closer look.

The neat thing about boxplots is that they not only provide a measure of
central tendency (the median value) they also give you an idea about the
distribution of the data. If the median line is more or less in the
middle of the box (between the upper and lower quartiles) and the
whiskers are more or less the same length then you can be reasonably
sure the distribution of your data is symmetrical.

If we want examine how the distribution of a variable changes between
different levels of a factor we need to use the formula notation with
the boxplot() function. For example, let’s plot our length variable
again, but this time see how this changes with each species. When we use
the formula notation with boxplot() we can use the data = argument to
save some typing. We’ll also introduce an x axis label using the xlab =
argument.

    boxplot(Petal.Length ~ Species, data = iris, 
             ylab = "Petal Length (cm)", xlab = "Species")

![](Intro2R_files/figure-markdown_strict/plot8-1.png)

As always, more information on plotting is available in the [full
tutorial](https://intro2r.com/graphics_base_r.html).

However, while these plotting with R’s built-in functions (also known as
“base R”) allows you to do a lot, it has its limits. To make even better
plots, we want to explore some add-on features. This brings us to the
concept of packages.

## R Packages

The base installation of R comes with many useful packages as standard.
These packages will contain many of the functions you will use on a
daily basis. However, as you start using R for more diverse projects
(and as your own use of R evolves) you will find that there comes a time
when you will need to extend R’s capabilities. Happily, many thousands
of R users have developed useful code and shared this code as
installable packages. You can think of a package as a collection of
functions, data and help files collated into a well defined standard
structure which you can download and install in R. These packages can be
downloaded from a variety of sources but the most popular are CRAN,
Bioconductor and GitHub. Currently, CRAN hosts over 15000 packages and
is the official repository for user contributed R packages. Bioconductor
provides open source software oriented towards bioinformatics and hosts
over 1800 R packages. GitHub is a website that hosts git repositories
for all sorts of software and projects (not just R). Often, cutting edge
development versions of R packages are hosted on GitHub so if you need
all the new bells and whistles then this may be an option. However, a
potential downside of using the development version of an R package is
that it might not be as stable as the version hosted on CRAN (it’s in
development!) and updating packages won’t be automatic.

To install a package from CRAN you can use the install.packages()
function. For example if you want to install the ‘ggplot2’ package enter
the following code into the Console window of RStudio (note: you will
need a working internet connection to do this):

    #if you do not have ggplot2 installed already, un-comment the following line and run this code snippet

    #install.packages('ggplot2')

Once you have installed a package onto your computer it is not
immediately available for you to use. To use a package you first need to
load the package by using the library() function. For example, to load
the ggplot2 package you previously installed:

    library(ggplot2)

The library() function will also load any additional packages required
and may print out additional package information. It is important to
realise that every time you start a new R session (or restore a
previously saved session) you need to load the packages you will be
using. We tend to put all our library() statements required for our
analysis near the top of our R scripts to make them easily accessible
and easy to add to as our code develops. If you try to use a function
without first loading the relevant R package you will receive an error
message that R could not find the function.

## Plotting with ggplot2

Now, we return to plotting.

For many people, using R to create informative and pretty figures is one
of the more rewarding aspects of using R. These can either take the form
of a rough and ready plot to get a feel for what’s going on in your
data, or a fancier, more complex figure to use in a publication or a
report.

Not only can R users make figures well suited for publication, but the
means in which the figures are produced also offers a wide-range of
customisation. This in turn allows users to create their own particular
styles and brands of figures which are well beyond the cookie-cutter
styles in more traditional point and click software. Because of this
inherent flexibility when producing figures, data visualisation in R and
supporting packages has grown substantially over the years.

In this section, we will focus on creating figures using a specialised
package called ggplot2.

The package ggplot2 was based on a book called Grammar of Graphics by
Leland Wilkinson (hence the gg in ggplot2). The Grammar of Graphics
approach moves away from the idea that to create, for example, a
scatterplot, users should click the scatterplot button or use the
scatterplot() function. Instead, by breaking figures down into their
various components (e.g. the underlying statistics, the geometric
arrangement, the theme), users will be able to manipulate each of these
components (i.e. layers) and produce a tailor-made figure fit for their
specific needs. Contrast this approach with the one used by, for
example, Microsoft Excel. The user specifies the data and then clicks
the scatterplot button. This inherently locks the user into many choices
made by the software developer and not the user. Think of how easily you
can spot an Excel scatterplot because other than a couple of pre-set
options, there’s really not much you can do to change the way the plot
displays the data.

The first step in producing a plot with ggplot() is the easiest! We just
need to install and then make the package avaialble. Luckily, we’ve
already done that by installing the package and loading it via library()
above! With that taken care of, let’s make our first ggplot. We will
continue using the iris dataset, and we will recreate some figures we
made in base R above. But we will build our plot from the ground up.

The simplest thing you can make in ggplot2 is a blank plot.

    ggplot()

![](Intro2R_files/figure-markdown_strict/gg1-1.png)

This obviously isn’t very helpful, so we’ll start adding some layers. We
can start by telling ggplot what dataset to use, and how to give it an
“aesthetic mapping”. That is, we tell it what visual quality it should
use to display different kinds of data. So, we can tell it we want to
use the X axis to visualize (or, “aesthetically map”) our Petal Length
data, and the Y axis to visualize our Petal Width data. Note that we can
do this before we’ve even added data points– we’re just told ggplot how
to map whatever data points we plot later. So, we wind up with this:

    ggplot(data=iris, mapping=aes(x=Petal.Length, y=Petal.Width))

![](Intro2R_files/figure-markdown_strict/gg2-1.png)

Geometries are the way that ggplot2 displays information. For instance
geom\_point() tells ggplot2 that you want the information to be
displayed as points (making scatterplots possible for example). Building
a ggplot is like adding layers when painting. Each time we want to
include a new layer we need to end a preceding layer with a + at the end
to tell ggplot2 that there are additional layers coming.

Let’s add some a points “geom” layer in order to produce a scatterplot:

    ggplot(data=iris, mapping=aes(x=Petal.Length, y=Petal.Width))+
      geom_point()

![](Intro2R_files/figure-markdown_strict/gg3-1.png)

If what we wanted was a quick and dirty figure to get a grasp of the
trend in the data we can stop here. From the scatterplot that we’ve
produced, we can see that petal width looks like it’s increasing with
length in a linear fashion. So long as this answers the question we were
asking from these data, we have a figure that is fit for purpose.
However, for showing to other people we might want something a bit more
developed. We could, for example, add some lines:

    ggplot(data=iris, mapping=aes(x=Petal.Length, y=Petal.Width))+
      geom_point()+
      geom_line()

![](Intro2R_files/figure-markdown_strict/gg4-1.png)

This isn’t so helpful, because geom\_line() is actually just playing
join-the-dots in the order they appear in the data. If we want to create
a line that shows us the trend, the geom we actually want to use is
called geom\_smooth(). We can fix that very easily just by changing
“line” to “smooth”.

    ggplot(data=iris, mapping=aes(x=Petal.Length, y=Petal.Width))+
      geom_point()+
      geom_smooth()

    ## `geom_smooth()` using method = 'loess' and formula 'y ~ x'

![](Intro2R_files/figure-markdown_strict/gg5-1.png)

There are lots of kinds of lines or trends we can use to display the
data. The way our line above was drawn was by using a method called
“LOESS” (locally estimated scatterplot smoothing) which gives something
very close to a moving average; useful in some cases, less so in others.
ggplot2 will use LOESS as default when you have &lt; 1000 observations
(something you can check in the function documentation, or using the
help function), but we can manually specify the method. Instead of a
wiggly line, we want a nice simple ‘line of best fit’ to be drawn using
a method called “lm” (short for linear model). Try looking at the help
file, using ?geom\_smooth, to see what other options are available for
the method = argument. While we’re at it, let’s get rid of the
confidence interval ribbon around the line. We can do this at the same
time as changing the method by setting the se = argument (short for
standard error) to FALSE.

    ggplot(data=iris, mapping=aes(x=Petal.Length, y=Petal.Width))+
      geom_point()+
      geom_smooth(method="lm", se=FALSE)

    ## `geom_smooth()` using formula 'y ~ x'

![](Intro2R_files/figure-markdown_strict/gg6-1.png)

The amazing thing about ggplot is you can rapidly, easily modify graphs
to map different elements of your dataset to different aesthetics. Or,
in other words, you can tell it to display different dimensions using
different methods of visualization. Let’s say we want to know which
species are which in the graph above. We can tell ggplot to map species
to something we can see, like a color or shape.

    #species mapped to color
    ggplot(data=iris, mapping=aes(x=Petal.Length, y=Petal.Width,
                                  color=Species))+
      geom_point()

![](Intro2R_files/figure-markdown_strict/gg7-1.png)

    #species mapped to shape. note you do not need to include "mapping="; ggplot understands this by default
    ggplot(data=iris, aes(x=Petal.Length, y=Petal.Width,
                                  shape=Species))+
      geom_point()

![](Intro2R_files/figure-markdown_strict/gg7-2.png)

Or, we can tell it that species should actually be displayed on the X
axis instead of Petal Length:

    #species mapped to color
    ggplot(data=iris, aes(x=Species, y=Petal.Width,
                                  color=Species))+
      geom_point()

![](Intro2R_files/figure-markdown_strict/gg8-1.png)

Maybe we want a scatterplot, but a different trendline for each species.
No problem.

    ggplot(data=iris, aes(x=Petal.Length, y=Petal.Width, color=Species))+
      geom_point()+
      geom_smooth(method="lm", se=FALSE)

    ## `geom_smooth()` using formula 'y ~ x'

![](Intro2R_files/figure-markdown_strict/gg9-1.png)

We can also tell ggplot to apply certain aesthetic mappings only to
certain geoms. So, let’s say we want color to apply to the lines, but
not to the points. We’ll take the color mapping out of the initial
ggplot() function and add it to the geom\_smooth() function.

    ggplot(data=iris, aes(x=Petal.Length, y=Petal.Width))+
      geom_point()+
      geom_smooth(aes(color=Species), method="lm", se=FALSE)

    ## `geom_smooth()` using formula 'y ~ x'

![](Intro2R_files/figure-markdown_strict/gg10-1.png)

What about making separate plots for each species? We can use “facets”,
which display the different “faces” of the data.

    ggplot(data=iris, aes(x=Petal.Length, y=Petal.Width))+
      geom_point()+
      geom_smooth(aes(color=Species), method="lm", se=FALSE)+
      facet_wrap(~Species)

    ## `geom_smooth()` using formula 'y ~ x'

![](Intro2R_files/figure-markdown_strict/gg11-1.png)

What if I want to see another variable, or a third dimension? No
problem, map it to something else you can visualize! For example, we can
vary the size of the points according to Sepal Width.

    ggplot(data=iris, aes(x=Petal.Length, y=Petal.Width))+
      geom_point(aes(size=Sepal.Width))+
      geom_smooth(aes(color=Species), method="lm", se=FALSE)+
      facet_wrap(~Species)

    ## `geom_smooth()` using formula 'y ~ x'

![](Intro2R_files/figure-markdown_strict/gg12-1.png)

What about a different kind of plot entirely? We just assign whatever
geoms we want, provided we have appropriate aesthetic mappings.

    #make a boxplot
    ggplot(data=iris, aes(x=Petal.Length, y=Petal.Width, color=Species))+
      geom_boxplot()

![](Intro2R_files/figure-markdown_strict/gg13-1.png)

    #make a histogram
    ggplot(data=iris, aes(x=Petal.Width, color=Species))+
      geom_histogram()

    ## `stat_bin()` using `bins = 30`. Pick better value with `binwidth`.

![](Intro2R_files/figure-markdown_strict/gg13-2.png)

    #make a density plot
    ggplot(data=iris, aes(x=Petal.Width, color=Species))+
      geom_density()

![](Intro2R_files/figure-markdown_strict/gg13-3.png)

These plots are endlessly modifiable. You can change titles, axes,
colors, legends, symbols, etc. etc. etc. You can also combine graphs,
and generate image files in different formats. Further description is
available through the [tutorial](https://intro2r.com/graphics_r.html)
and a really handy source is the ggpplot Cheat Sheet which is available
if you scroll down on [this page](https://ggplot2.tidyverse.org/); it’s
a neat, handy summary of all the different geoms you can use, and all
the syntax and modifications you need.

## Statistics in R

In addition to R’s powerful data manipulation and graphics facilities, R
includes a host of procedures which you can use to analyse your data.
Many of these procedures are included with the base installation of R,
however, even more can be installed with packages available from the
CRAN website.

We will look at this very briefly; as always, more detail is available
in [the full tutorial](https://intro2r.com/stats_r.html).

Let’s say we want to check whether the iris petal lengths are
significantly different between two species. Let’s make two vectors, for
the petal length of the setosa and versicolor species. We can test this
using a t-test, which we run with the simple function t.test()

    setosa_petal_length<-iris[iris$Species=="setosa", "Petal.Length"]
    setosa_petal_length

    ##  [1] 1.4 1.4 1.3 1.5 1.4 1.7 1.4 1.5 1.4 1.5 1.5 1.6 1.4 1.1 1.2 1.5 1.3 1.4 1.7
    ## [20] 1.5 1.7 1.5 1.0 1.7 1.9 1.6 1.6 1.5 1.4 1.6 1.6 1.5 1.5 1.4 1.5 1.2 1.3 1.4
    ## [39] 1.3 1.5 1.3 1.3 1.3 1.6 1.9 1.4 1.6 1.4 1.5 1.4

    versicolor_petal_length<-iris[iris$Species=="versicolor", "Petal.Length"]
    versicolor_petal_length

    ##  [1] 4.7 4.5 4.9 4.0 4.6 4.5 4.7 3.3 4.6 3.9 3.5 4.2 4.0 4.7 3.6 4.4 4.5 4.1 4.5
    ## [20] 3.9 4.8 4.0 4.9 4.7 4.3 4.4 4.8 5.0 4.5 3.5 3.8 3.7 3.9 5.1 4.5 4.5 4.7 4.4
    ## [39] 4.1 4.0 4.4 4.6 4.0 3.3 4.2 4.2 4.2 4.3 3.0 4.1

    t.test(versicolor_petal_length, setosa_petal_length)

    ## 
    ##  Welch Two Sample t-test
    ## 
    ## data:  versicolor_petal_length and setosa_petal_length
    ## t = 39.493, df = 62.14, p-value < 2.2e-16
    ## alternative hypothesis: true difference in means is not equal to 0
    ## 95 percent confidence interval:
    ##  2.656382 2.939618
    ## sample estimates:
    ## mean of x mean of y 
    ##     4.260     1.462

We can also run statistical tests using formula notation. Let’s look
whether petal length is significantly different between all three
species.

    model<-aov(data=iris, Petal.Length~Species)

    summary(model)

    ##              Df Sum Sq Mean Sq F value Pr(>F)    
    ## Species       2  437.1  218.55    1180 <2e-16 ***
    ## Residuals   147   27.2    0.19                   
    ## ---
    ## Signif. codes:  0 '***' 0.001 '**' 0.01 '*' 0.05 '.' 0.1 ' ' 1

Is petal length a significant predictor of petal width? We can run a
linear model.

    lin_model<-lm(data=iris, Petal.Width~Petal.Length)

    summary(lin_model)

    ## 
    ## Call:
    ## lm(formula = Petal.Width ~ Petal.Length, data = iris)
    ## 
    ## Residuals:
    ##      Min       1Q   Median       3Q      Max 
    ## -0.56515 -0.12358 -0.01898  0.13288  0.64272 
    ## 
    ## Coefficients:
    ##               Estimate Std. Error t value Pr(>|t|)    
    ## (Intercept)  -0.363076   0.039762  -9.131  4.7e-16 ***
    ## Petal.Length  0.415755   0.009582  43.387  < 2e-16 ***
    ## ---
    ## Signif. codes:  0 '***' 0.001 '**' 0.01 '*' 0.05 '.' 0.1 ' ' 1
    ## 
    ## Residual standard error: 0.2065 on 148 degrees of freedom
    ## Multiple R-squared:  0.9271, Adjusted R-squared:  0.9266 
    ## F-statistic:  1882 on 1 and 148 DF,  p-value: < 2.2e-16

Understanding and interpreting the statistical tests here is beyond the
scope of this tutorial. Learning how to conduct proper statistical
analysis of data should be covered in other courses, or in more
extensive trainings, books, etc. However, this should give you a glimpse
into the types of data analyses you might be able to conduct in R. Much
more complicated, scenario-specific tests and analyses are available
through packages, which tremendously expand the capability to use R for
all sorts of data analysis and intepretation.

## Conclusion

This is the end of our crash-course intro to R!

As we said at the start, the best way to learn R is to use it, and you
can always use your existing code (including this tutorial), and endless
online resources, in order to write your own code!

Online forums are tremendously helpful (chances are, someone has asked
your exact question, and it’s likely someone has written a super helpful
answer on a forum like Stack Overflow– there is an amazing user
community and lots of people dedicated to helping others use these
tools!). And, new AI tools, such as ChatGPT, can be helpful in
generating or troubleshooting your code, explaining your code to you, or
serving as effective coding “partners”.

Take care in using all of these resources– you want to spend the time to
understand what your code is doing, so you can interpret its output and
make sure it’s doing what you *think* it’s doing, and what you *want* it
to do. But, these tools will set you on your way to becoming a competent
programmer, and allow you to answer all sorts of interesting, exciting
questions!

Happy coding!
