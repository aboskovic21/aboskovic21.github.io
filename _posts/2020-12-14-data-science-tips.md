---
layout: post
---

# Intro to Debugging

This fall, I had a lot of fun TA-ing Data Science (STAT 231) at Amherst. The course was taught in R, and, understandably, students who were using R for the first time struggled with debugging errors. I'm writing this short post about debugging code in R to help people get started. Note that I'll assume some basic working knowledge of R, [ggplot](https://ggplot2.tidyverse.org/reference/ggplot.html), and dplyr (`mutate()`, `select()`, etc.) 

## 1. Google is your best friend!

When I first started coding with R, I thought that googling how to do stuff might be a violation of the honor code. I was *so* wrong. You can't do any data science without googling! In fact, my data science professor always said "don't ask me any questions until you've gone through the first three pages of google." Now, whenever I come across something that I don't initally know how to do, my first instinct is to open a new tab and google it. 

You'll probably see some of the same coding resources pop up when you google, including [Stack Overflow](https://stackoverflow.com/). This site often has great suggestions for common coding mistakes and ideas for how to implement different things, so use this resource. Keep in mind that you should always cite others' work in assignments and projects. 

## 2. Pay Attention to Variable Types

In your environment, you should be able to see the "type" of each object you create. These variable types can be numerics, integers, characters, lists, arrays, matrices, just to name a few. A more complete list with some explanations is available [here](https://www.tutorialspoint.com/r/r_data_types.htm). 

You might be wondering where the coding errors come into play here, then. Let's think about this with an exmaple. Suppose we have a dataset where one of our variables indicates gender with "M" or "F," but the variable type of that column is a character. If we want to make a bar graph to show frequency of genders, then we're going to run into some problems! R is going to give us an error because it doesn't know how to make a bar graph with characters. It needs a specific variable type in this case: a factor. Luckily, this problem is easy to solve because we can just make the whole column a factor with the `as.factor()` function. Then, we can use this new *mutated* column to make our graph!

Basically, if you're getting some variable type error, try this workflow:
- `as.____()`, where the blank represents what you're trying to transform your column into. You can do this with a call to `mutate()`. 
- Check that your column is actually the type you want it to be. Try typing `typeof(dataset$column)` into the console, where "dataset" and "column" are the names of the dataset and column of interest, respectively.
- If the call to `typeof()` gave you the type you wanted, you're all set. If not, that's weird. Try googling it! 

## 3. Object/Function not Found

These errors are pretty easy to deal with. If your function isn't found, then you probably haven't loaded the package you need in order to call that function. Try `library(package_name)`. If that doesn't work, i.e., it tells you that that package doesn't exist then you have to install the package with `install.packages()`. Don't worry, it's totally normal not to know which package functions belong to- a quick google search will help you out. I usually like to check the R documentation for these. For the `mutate()` function, for example, the R documentation looks like [this](https://www.rdocumentation.org/packages/dplyr/versions/0.5.0/topics/mutate). Notice that the top right corner of the page says "From dplyr." That's how you know what package the function comes from.

With object not found errors, though, that probably means you cleaned your environment a little bit ago and you're trying to use an object that no longer exists in your environment. You can hit the down arrow pointing to a green line between the green play button and settings icon in the upper right corner of the R chunk you're working on. This will run all of the code above the current chunk, *not including* your current chunk. Now, you should be up to date and your error should be gone!

## 4. Miscellaneous Tips and Tricks in R

I also have some quick miscellaneous tips that I swear by but don't really merit a whole blurb.

**1. Check your spelling!** Make sure you spell your variable names and function names right. It sounds silly, but I've made that mistake plenty of times and kicked myself when I figured out the problem after 15 minutes.

**2. Make your code readable and pretty.** Instad of manually going through and spacing, you can do this quickly with R Styler. Install `styler` using `install.packages(styler)`. Highlight the code chunk you want to style. Then, you should be able to go to "Addins" at the top of your R window, which opens a dropdown. Under the "Styler" section, click "Style selection." Boom! Readable code!

**3. Set the right directory.** R won't be happy if you aren't working in the "right place," so make sure you're working in the directory where your file is located. Want to do that quickly? At the top of the R window, click Session --> Set working directory --> To source file location. Done! You can even check that it worked with `getwd(file_name)`.

**4. Keyboard shortcuts.** To run code, you can just hit *command* + *return* on Mac or *control* + *enter* on Windows. You can even highlight multiple lines and then use that sequence to run multiple lines! To make a new code chunk, use *command* + *option* + *I* on Mac or *control* + *alt* + *I* on Windows. These arehuge time savers in the long run!
