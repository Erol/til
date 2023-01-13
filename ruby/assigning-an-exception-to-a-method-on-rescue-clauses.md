# Assigning An Exception To A Method On Rescue Clauses

Assigning an exception to a local variable is a well-known pattern in Ruby. Here's an example:

```
begin
  raise StandardError
rescue StandardError => error
  puts "An exception was encountered: #{error}"
end

#=> An exception was encountered: StandardError
```

Using a method to "capture" the exception is relatively unheard of though, and I have not seen this documented anywhere. Imagine doing this:

```
def error=(value)
  puts "An exception was encountered: #{value}"
end

begin
  raise StandardError
rescue StandardError => self.error
end

#=> An exception was encountered: StandardError
```

