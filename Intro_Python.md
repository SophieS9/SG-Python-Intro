---
layout: page
title: Introduction to Python
visible: false
tags:
  # languages
  - python
  # levels
  - beginner
---
<!-- change visible to true if you want it on the site -->

 - **Author**: [Dr. Sophie Shaw](https://github.com/SophieS9) 
 - **Research field**: Bioinformatician working on analysis of Next Generation Sequencing Data

# Introduction to Python Programming

When many researchers decide to start learning programming, their language of choice is often Python. This tutorial aims to introduce the Python language, show you what it can do, when you'll want to use it and introduce some basic concepts. This is just a starter and you WILL NOT be an expert within the next hour, but hopefully you'll know how to get started and how to go about learning more skills.

## How Can I Use Python On My Computer?

If you're using a Mac or Unix operating system, python is mostly likely already installed on your computer. To double check and find out which version you have, open up a terminal window and simple type:
```
python --version
```

If you're using Windows, you'll need to download software that allows you to run python. Today we're going to use [spyder](https://github.com/spyder-ide/spyder) as it has a nice graphical user interface (GUI), similar to RStudio. I would recommend the installation option via Anaconda. Mac and Unix users can also download this software if they'd prefer to use the GUI. 

Once installed, launch spyder. On a Windows machine *DO THIS*. If you have installed with Anaconda on a Mac or Unix platform, you can launch spyder from the command line as follows:
```
spyder&
```
NOTE! The & sign at the end allows spyder to run in the background so you can still use your terminal window for other things. 

A window that looks something like this should have opened:

<img src="./Images/spyder_open.png"/>

* The left hand side is your Script editor. Here you can write and edit your python code, and when it's ready, send it to the Console to run. You can save your scripts so that you can come back to them at a later date to re-run them or to send them to other researchers. 
* The top right hand window has three tabs - Object inspector (This contains all of the objects you have created), Variable explorer (This contains all of the variables you have created) and File explorer (this shows all of the files in your current working directory). Today, you're going to want to viewing the Variable explorer tab. I'll explain more about this a little later. Your tab bar will look like this:
    <p align=center>
    <img src="./Images/variable_explorer.png"/>
    </p>		
* The bottom right hand side is the Console. This is where yout script will run. There are three tabs to this window, two console types (Console and IPython Console) and the history tab. We're going to want to have the Console tab open. It should look like this:
    <p align=center>
    <img src="./Images/console.png"/>
    </p>

### Python Version 2 vs. Python Version 3
If possible when installing, you should install python 3 as this is the most up-to-date version. However some users may already have python 2 installed or prefer to use python 2. There are some functional differences between the two (see [here](https://wiki.python.org/moin/Python2orPython3) for more details) but today it shouldn't matter too much which version you have. I'll point out any differences during the tutorial. 
 
## So Let's Get Started!

In this tutorial, I'm going to introduce a few basic concepts to get you started with pythons. You might not get through all of these in an hour, but don't worry! These are:
1. Variables - what they are and how to declare them
2. Arithmetic - using python to do some simple equations
3. Strings - and the cool stuff you can do with them
4. Lists - lists of variables
5. Loops - doing the same thing lots of times
6. Syntax - tabs, line breaks, comments]

### 1. Variables - what they are and how to declare them

Variables are ways to store information in python. This information can be text (a.k.a a string), numbers or something with a much more complex structure (see Lists to get an idea). This information can then be accessed by the script by using the variable name. Creating a variable is very simple. We have to give it a name. This should be unique, informative and, preferably in python, lower case. We then use an equals sign (=) to give it the information.

We're now going to get started with writing our first python script. In this script we're going to declare a variable with the name "text" that holds the string "Hello World!". Then we're going to use the print function to print this variable in the console. In the Editor window on the left hand side of spyder, type the following:
```
text = "Hello World!"

print text
```

You can then run your script by clicking on the "Run" green arrow in the top bar:
<p align=center>
<img src="./Images/run_arrow.png"/>
</p>

When you run a script for the first time you'll be asked to save it. Choose an appropriate name and location and save the file. 

You'll notice that your console has now changed:
<p align=center>
<img src="./Images/variable_out.png"/>
</p>
The text has been printed in the console. Throughout the tutorial this is going to be the pattern we follow. Edit the script, run in the console, look at what is printed to the console. 

Now we've made our first variable, go back to your script and edit it as follows:
```
text = "Hello World!"
integer = 1
float = 2.35

print text
print integer
print float
```

Here I've introduced two new variable types - integers (whole numbers) and floats (decimal numbers). 

Run your script and look at the changes in the console. 

Within your script you can declare as many variables as you like as long as the name is unique. Now we'll take a look at some of the things you can do with these variables.

### 2. Arithmetic - using python to do some simple equations

For this section you can either edit your existing script or open a new one. Type the following:
```
x = 5
y = 6

print x + y
``` 
Run the script (you'll need to save it first) and look at the changes in the console. The result of adding 5 and 6 has been printed.

Alternatively you could have done the following:
```
x = 5
y = 6
z = x + y

print z
```

As well as addition, you can do subtraction, multiplication, division, raise a number by a power (**) and obtain the modulo (%) (the remainder when dividing by a number). Have a go at the example. Change the numbers to whatever you like:
```
x = 5
y = 6

print x + y
print x - y
print x * y
print x / y
print x ** y
print x % y
```

If you're using Python version 2, you might have noticed something unusual with the results above. When you divide 5/6 the result is printed as 0 when we all know that the result should be 0.833333. This is because division of integers in Python 2 is automatically rounded.

To fix this, add the following to the top of your script
```
from __future__ import division
``` 
This imports the "division" function from the future module which corrects division to "floating point" in Python 2. This is automatically implemented in Python 3. 

NOTE! Python (and other programming languages) have limitions when using arithmetic functions on floating point (decimal) numbers. This is because of the way numbers are stored in binary, they are always just the closest estimation to the floating point. This post [HERE](https://docs.python.org/3/tutorial/floatingpoint.html) explains this a lot better although it does talk about binary! It's nothing to worry about today but it's something that you should be aware of. 

To be able to perfrom mathematical arithmetic on variables, they need to be of the same type. For instance, you can't add an integer and a string:
```
x = 5
y = "Banana"

print x + y
```

When doing this you should have seen an error that looks like this in the console:
<p>
<img src="./Images/adding_error.png"/>
</p>

Error messages in Python are great for telling you what is wrong and where in the script the error has occurred. Here it is telling us that it is unable to add an integer (int) and a string (str) and that the error occurs on line 12 of the script. You should make yourself familiar with error messages. The more coding you learn, the more you will see them!
 
### 3. Strings - and the cool stuff you can do with them

As well as being great at working with integers, Python also allows us to work with and manipulate strings. Let's go back to the first variable we declared:
```
text = "Hello World!"

print text
```

Python has some built in functions that allow us to work with strings. This includes calculating the length of the string, changing the string to upper case or changing the string to lower case. The syntax (the correct way to write) each function is slightly different. The length function follows the syntax "len(VARIABLE)" whereas the lower and upper functions follow the syntax "VARIABLE.function()". See by running the example below:
```
text="Hello World!"

print text
print len(text)
print text.upper()
print text.lower()
```

There are other built in functions available as well including a function to capitalize the first letter or to swap the cases of all letter. 

As well as manuipulating strings, Python can be used to concatenate strings together, like in this example:
```
fruit="Apples"
vegetable="Potatoes"

shoppinglist = fruit + vegetable

print shoppinglist
```

You should have noticed that the output above isn't formatted particularly nicely. I'd like my shopping list to have spaces in between the items. Therefore I can edit the script as follows, adding a space between the variables:
```
fruit="Apples"
vegetable="Potatoes"

shoppinglist= fruit + " " + vegetables

print shoppinglist
```

But what about if I wanted to add have each item of my shopping list on a new line? Well instead of adding a space, we can add a new line character - "\n". There are a series of special characters in programming that are used to specify different things such as new lines (\n), tabs (\t), spaces (\s) and so on. These are known as escape characters and also start with a back slash. 
```
fruit="Apples"
vegetable="Potatoes"

shoppinglist= fruit + "\n" + vegetables

print shoppinglist
```

Indexing

### 4. Lists - lists of variables

Other data types

### 5. Loops - doing the same thing lots of times

Conditional Statements

### 6. Syntax - tabs, line breaks, comments

## How Can I Continue Learning Python?!

There are some great free online resources available to help you learn Python (and many other languages). Two of my favourites are:

* [Codecademy](https://www.codecademy.com/learn/python). This has a Python tutorial as well as tutorials in other languages with a focus upon website design. There are free accounts or paid-for accounts with added functionality. 
* [HackerRank](https://www.hackerrank.com/). This has tutorials in many different languages as well as coding competitions. It's used by companies to head hunt the best new developers.

If you're willing to spend a little money there are also several good text books available, most of which come with downloadable or online content. An example of some include:

* [Python for Biologists](http://pythonforbiologists.com/). Excerpts of the text are available online for free.  
* [Learn Python the Hard Way](https://learnpythonthehardway.org/). You can try this one out for free before purchasing.  

The more you learn to program, the more you will realise that Google is your best friend! If you're having a problem, Google it. It's likely that someone has posted the answer already on the many forums available online. 
