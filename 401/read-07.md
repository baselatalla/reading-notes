# Understanding Scope

1. Global scope: The names that you define in this scope are available to all your code.

2. Local scope: The names that you define in this scope are only available or visible to the code within the scope.


# Names and Scopes in Python

Since Python is a dynamically-typed language, variables in Python come into existence when you first assign them a value. On the other hand, functions and classes are available after you define them using def or class, respectively. Finally, modules exist after you import them. As a summary, you can create Python names through one of the following operations:

Operation	Statement
Assignments	x = value
Import operations	import module or from module import name
Function definitions	def my_func(): ...
Argument definitions in the context of functions	def my_func(arg1, arg2,... argN): ...
Class definitions	class MyClass: ...