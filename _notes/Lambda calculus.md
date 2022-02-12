---
layout: post
title: "Lambda calculus"
---

# Lambda calculus
## Variables
Variables are written as
`λx`, `λy` etc.

## Constructing functions
In lambda calculus, functions are written as constructed:

`λx.<some function of x >`
For example, a function
`f(x) = x + 1`
would be written as:
`λx. x + 1`
Functions only have a single input, and so
`f(x, y) = x + y`
Would be represented as 
`λx.(λy.x + y)` 
`λx.λy. x + y`
This is very subtle, but essentially breaks down a function into substituting a single input at a time. This is known as ‘currying’.
## Applying functions
Functions are applied via substitution. For example
```
(λx. x + 1) 5
= (5 + 1)
= 6
```
Or in the case of `f(x, y) = x + y` for `x = 2`, `y = 3`, we would have:
```
((λx.λy. x + y)2)3
= (λy. 2 + y)3
= 2 + 3
= 5
```

### Conventions
- functions are applied ‘left associative’ without further parentheses, i.e.
	`X Y Z = ((X Y) Z)`
- the ‘body’ of the expression extends as far right as possible without further parentheses, i.e.
	`λx. Y Z = λx. (Y Z)` 


## Why is this useful
-  You can encode any computation in lambda calculus
- equivalent to a Turing machine
	- a Turing machine program can be translated into a lambda calculus program and vice-versa
- basis for functional programming languages
## Encoding Boolean variables
```
True = λx.λy.x
False = λx.λy.y
```

With this defined, `Not` can be defined as follows:
```
Not = λb.b False True
	  = λb.((b False) True)
```
To prove this, let’s apply `Not` to both `True` and `False`.
Applied to `True`:
```
Not True = ( λb.b False True) True
	= True False True
	= ((True) False) True
	= ((λx.λy.x) False) True
	= (λy.False) True
  = False
```
Similarly,
```
Not False = ( λb.b False True) False
	= False False True
	= λx.λy.y False True
	= λy.y True
	= True
```


#notes/random