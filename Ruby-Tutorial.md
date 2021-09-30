# Ruby How To

This tutorial will outline how to program using the language Ruby and would not be possible without existing sources. To create this tutorial I used a combination of online articles and textbooks offered through the ACM. Like Tutorialspoint's overview of ruby  (https://www.tutorialspoint.com/ruby/index.htm) and Beginning Ruby 3: From Beginner to Pro by Carleton DiLeo and Peter Cooper on the O'riley website (https://www.oreilly.com/library/view/beginning-ruby-3/9781484263242/) and the official Ruby documentation (http://ruby-doc.com/docs/ProgrammingRuby/).

## History

First, let's go over some history about the programming language Ruby. Ruby was created in the mid-1990s and released in 1995 by Yukihiro "Matz" Matsumoto. Matsumoto created the language as a general purpose language that is a mashup of some of his existing favorite languages. Like Perl, Smalltalk, Eiffel, Ada, and Lisp. While Ruby itself is general purpose, a framework built off of it is used to build web pages, Ruby on Rails. And specific projects built using Ruby include GitHub and Airbnb.

## Getting Started

First, lets install Ruby. 

Go to https://rubyinstaller.org/downloads/ and select the latest version of Ruby with the Dev kit. Then install VSCode and the Ruby extension found in VSCode's extension library. For this tutorial I chose to use VSCode as the IDE because Ruby does not have a recommended environment and VSCode is free and a popular choice for many programmers. To actually run Ruby there are two options. One, you can install the Code Runner extension offered through VSCode. Or, two, run Ruby from the terminal using the 'ruby' connamd. Now you are all set to begin coding!

For an example of Ruby code you can go to helloWorld.arb. This program shows you how to print 'Hello World' and make comments. (Comments are made using the hash/pound symbol. Similar to how Python uses comments.)

## Data Types and Naming Conventions

Variables in Ruby can be named using alfanumeric characters and underscores. However, they cannot start with numbers or capital letters and identifiers that start with capitals will be considered constants by the Ruby compiler. It is also useful to know that Ruby is strongly and dynamically typed. This means that Ruby will not automatically convert variables from one type to another (strongly) and check for type errors during run-time (dynamically). An example of this is that the statement x = "5" + 6 will throw a type error. This is because type string cannot be added or concatenated to type integer. This is because Ruby is strongly typed. But since it is dynamically typed the type of "5" can be changed to integer, and in that case the expression would run.

Another thing to consider while declaring variables is what data type they will store. While in Ruby you do not need to declare the type when instantiating a variable it is still advantageous to think about it. The available primitive data type are integer, string, and floating point numbers. The available complex data types are arrays, hashs, ranges, regex expressions, and symbols. 

Lastly, the documentation on Ruby does not mention the limitations in great detail. The biggest limitation to watch out for, though, is type errors like you cannot add/concatanate unlike variables with each other.

For examples on how to declare variables and how they can be used refer to dataTypes.arb.

## If/else, Switch-Case, and Logical Expressions

### Boolean Logic

In Ruby the boolean values are true and false or nil. False and nil can be used interchangeably. An interesting note that will be useful later, since Ruby is built on objects any object that is not assigned nil or false will be considered true.

### If/else and Switch-Case Statements

In Ruby the conditional statements are if/elsif/else and unless. Unless acts as the opposite of if, so in other word it is doing this: if this statement is not true do this block of code, but if it is run the code in the else. You can also use the keyword then in if/unless statements if the succeeding code is only one line. Also, Ruby solves the dangling else issue by using an ending statment. In this case it is 'end' after the else.

Ruby also allows for the use of the logical device short circuit evaluation. This happens when using the and expression the second argument is only evaluated when the first argument evaluates to true.

Another conditional logic device Ruby offers is the case statement. Case statements take in an argument and evaluate it against several cases, if one evaluates to true the code under the case runs. For case expressions you do not have to use break to exit from a case and does not have use of continue to force evaluation of all cases.

For examples, refer to if-else.arb and switch.arb.

## Loops

Ruby has three different kinds of loops: while/until loops, for-in loops, and basic iterator functions.

### While loop:
A while loop in Ruby executes a chunck of code *while* a condition is true.
```
while conditional [do]
  # code to be executed
end
```

### Until loop:
An until loop Ruby executes a chunk of code *until* a condition is met.
```
until conditional [do]
  # code to be executed
end
```

### For-in loops:
These loops "walk" over any object that respond to the each() function. So this is objects like arrays and ranges.
```
for i in expression [do]
   # code to be executed
end
```

### Iterator method loops:
Ruby has methods that execute a block of code for a specified number of times. The iterators are .upto(), .times(), .step(), .each(), and loop.
```
a.iterator do |variable|
  # code to be execute
end

or

loop {
  # code to be executed
}
```

\* It should be noted that the Ruby documentation asserts that it does not have for loops in the way that C-family languages do, and that for-in loops are just "syntactic sugar" and act much like the .each() iterator.

## Functions

Functions in Ruby are referred to as methods. They are declared using the def keyword, the method name in camel case, and the arguments in parentesis. Mehtods can be names using letters and either a trailing ! to indicate the method modifies the reciever or a trailing ? to indicate that the method acts as a query. They also can be placed in any part of the program. Like this:
```
def myMethod(arg1, arg2, arg3)
  # Code for the method
  return
end
```
Ruby methods both accepts multiple arguments of mixed types and retruns multiple variables of mixed types. Although Ruby does return multiple arguments they do get stored in one variable as a string that must be split after the fact.

When passing variables into a method in Ruby it is important to remember that it depends on the data type. Primitive data types are pass by value and complex data types are pass by reference. The file reference.arb illustrates this. Some people will say that Ruby is pass by object (since everything is an object) or pass by value but the value is a reference; these people are being needlessly pedantic and the thing that physically gets passed is a location in memory. So, Ruby, functionally, is both.

Recursion is also allowed in Ruby.

## Classes and Inheritance
Ruby is an Object-Oriented programming languange. A class in Ruby is created using the key word class and a name strting with a capital letter. Then initializing the class attributes using the method initialize, which is built in method that does the same thing across all Ruby objects. The instance variables are stored starting with an @. As seen here:
```
class Name
  def initialize(attr1, attr2)
    @var1 = attr1
    @var2 = attr2
  end
end
```
You can also add a .to_s method which is used to convert objects to readable strings across all classes as well.


#### Citations:
* https://www.ruby-lang.org/en/about/
* https://rubyonrails.org/
* https://www.rubyguides.com/2019/11/what-can-you-do-with-ruby/
* https://about.gitlab.com/blog/2018/10/29/why-we-use-rails-to-build-gitlab/
* https://github.blog/2020-08-25-upgrading-github-to-ruby-2-7/
* https://railsware.com/blog/famous-web-apps-built-with-ruby-on-rails/
* https://en.wikipedia.org/wiki/Airbnb
* https://www.dummies.com/programming/ruby/how-to-install-and-run-ruby-on-windows/
* https://www.rubyguides.com/2019/02/ruby-ide/
* https://learning.oreilly.com/library/view/beginning-ruby-3/9781484263242/html/340896_4_En_3_Chapter.xhtml
* http://ruby-doc.com/docs/ProgrammingRuby/
* https://zetcode.com/lang/rubytutorial/variables/
* http://www.rubyfleebie.com/2007/07/09/ruby-is-dynamically-and-strongly-typed/
* https://www.techotopia.com/index.php/Understanding_Ruby_Variables
* https://www.geeksforgeeks.org/ruby-loops-for-while-do-while-until/
* https://www.geeksforgeeks.org/ruby-types-of-iterators/
* https://www.geeksforgeeks.org/recursion-in-ruby/
* https://launchschool.medium.com/object-passing-in-ruby-pass-by-reference-or-pass-by-value-6886e8cdc34a
* https://learn.co/lessons/pass-by-reference
