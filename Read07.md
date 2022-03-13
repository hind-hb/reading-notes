## Python Scope 

The concept of scope rules how variables and names are looked up in your code. It determines the visibility of a variable within the code.
The scope of a name or variable depends on the place in your code where you create that variable. 
The Python scope concept is generally presented using a rule known as the LEGB rule.

The letters in the acronym LEGB stand for Local, Enclosing, Global, and Built-in scopes.
This summarizes not only the Python scope levels but also the sequence of steps that Python follows when resolving names in a program

 Global scope: The names that you define in this scope are available to all your code.

 Local scope: The names that you define in this scope are only available or visible to the code within the scope.

Scope came about because early programming languages (like BASIC) only had global names. With this kind of name, any part of the program could modify any variable at any time
, so maintaining and debugging large programs could become a real nightmare. To work with global names,
you’d need to keep all the code in mind at the same time to know what the value of a given name is at any time. This was an important side-effect of not having scopes.

The global statement can be used to modify global names from almost any place in your code, as you’ll see in The global Statement. Modifying global names is generally considered bad programming practice because it can lead to code that is:

Difficult to debug: Almost any statement in the program can change the value of a global name.

Hard to understand: You need to be aware of all the statements that access and modify global names.

Impossible to reuse: The code is dependent on global names that are specific to a concrete program.

The nonlocal names can be accessed from inner functions, but not assigned or updated. If you want to modify them, then you need to use a nonlocal statement.
With a nonlocal statement, you can define a list of names that are going to be treated as nonlocal.
