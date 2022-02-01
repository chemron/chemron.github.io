---
layout: post
title:  "Blocks, Procs and Lambdas in Ruby."
---

Below is a small summary of Blocks, Procs and Lambdas in Ruby.  
Up first, we have Blocks:

## Blocks

Blocks are bits of code that can be put after an enumerator and iterate
through it in the format:

```ruby
[enumerator] {|x, y, ...| ... }
```

or

```ruby
[enumerator] do |x, y, ...|
    ...
end
```

For example

```ruby
[[1, 2], [2, 3], [3, 4]].each {|x, y| puts x*y}
```

can also be written as

```ruby
[[1, 2], [2, 3], [3, 4]].each do |x, y|
    puts x*y
end
```

and will output

```shell
2
6
12
```

while

```ruby
3.times {puts "hello"}
```

or

```ruby
3.times do
    puts "hello"
end
```

Will output:

```shell
hello
hello
hello
```

### Yielding to Blocks

Methods can also accept blocks by making use of the `yield` command. If used in
a method, control can be 'yielded' to the block mid execution. For example, if
we have a method:

```ruby
def do_three_times
    for _ in 1..3
        yield
    end
end
```

we can call it with a block as follows:

```ruby
do_three_times {puts "hi"}
```

or, equivalently,

```ruby
do_three_times do
    puts "hi"
end
```

to get the output:

```shell
hi
hi
hi
```

You can also yield values, for example:

```ruby
def yield_i
    for i in 1..3
        yield i
    end
end

yield_i {|x| puts x}
```

will produce the output:

```shell
1
2
3
```

What if you want to reuse a block though? For this purpose, we use procs.

## Procs

Unlike blocks, procs are objects and can therefore be used multiple times.
Procs can be defined as follows:

```ruby
my_proc = Proc.new [block]
```

where `[block]` is any block, for example:

```ruby
{|x| puts x}
```

Procs can be converted to blocks by using the '`&`' symbol, like follows:

```ruby
3.times &my_proc
```

For example, if we can make a proc that doubles given numbers, i.e.

```ruby
doubler = Proc.new {|x| x*2}
```

Which we could then use to double each element in a list:

```ruby
doubled_list = [1, 2, 3].collect &doubler
```

A proc can also be turned in a method, by using the `.call` method. For example,
in the following snippet:

```Ruby
my_proc = Proc.new {|x| puts x}

my_proc.call "Hello"
```

the proc `my_proc` is converted into a method using `my_proc.call`, which is
given the input `"Hello"`. This would then 'put' `"Hello"` to the console.

## lambdas

Lambdas are very similar to procs. While procs are defined as follows,

```ruby
Proc.new [block]
```

Lambdas are defined by:

```ruby
lambda [block]
```

like procs, lambdas can be converted to a method using the `.call` method, and
can be used as a block with the `&` symbol. There are however a few small
differences between procs and lambdas.

### Differences between procs and lambdas

There are two main differences between implementing lambdas and procs.

1. a lambda checks the number of arguments passed into it, and will throw an error
   if it is given the wrong number of inputs. A proc on the other hand will not
   check, and assigns `nil` to any missing arguments.
2. `return`  in a lambda will pass control back to where it was called from.
   `return` in a proc will return 'fully', without going back to a method it was
   called from.

for example, the function:

```ruby
def test_return_lambda
    my_lambda = lambda {return "I'm in the block"}
    my_lambda.call
    "I'm in the method"
end
```

will return the string `"I'm in the method"`, while the function

```ruby
def test_return_proc
    my_proc = Proc.new {return "I'm in the block"}
    my_proc.call
    "I'm in the method"
end 
```

will return the string `"I'm in the block"`.
