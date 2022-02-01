---
layout: post
title:  "Loops and Iterators in Ruby"
date:   2021-11-14 12:00:00 +1100
---

There are many ways to loop or iterate in ruby, so I put together a small
summary.

## Enumerator loops

```ruby
[enumerator] do |x|
    ...
end
```

or

```ruby
[enumerator] {|x| ... }
```

or

```ruby
for x in [enumerator] do
    ...
end
```

where `[enumerator]` is a given enumerator, for example:

- `loop`
- `1...2.each`
- `2.times`
- etc.

(`for` can also be used with an 'iterable' for example `[1, 2]` or `1..2`)

## non-enumerator loops

The following four examples 'put' the numbers from 1 to 10 in the terminal

```ruby
i = 1
while i <=10
    puts i
    i += 1
end
```

```ruby
i = 1
until i == 11
    puts i
    i += 1
end
```

```ruby
i = 1
loop do
    puts i
    i += 1
    break if i==11
end
```

```ruby
for i in 1..10
    puts i
end
```
