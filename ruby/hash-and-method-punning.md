# Hash And Method Punning

Ruby 3.1 introduced an updated syntax to write shorthand hashes which allows us to ommit the variable if it has exactly the same name as the hash key, similar to Javascript's object punning. Here's an example:

```
a = 1
b = 2

{ a:, b: } #=> { a: 1, b: 2 }
```

And this also applies to method keyword arguments:

```
def foo(a:, b:)
  { a:, b: }
end

a = 1
b = 2

foo(a:, b:) #=> { a: 1, b: 2 }
```

The shorthand syntax also accepts methods without parameters in lieu of variables:

```
def foo
  1
end

{ foo: } #=> 1
```

