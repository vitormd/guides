#Coding Style
- Use 2 spaces for indentation, no tabs.
- Use spaces around operators, after commas, colons and semicolons, around { and before } and =.
```ruby
sum = 1 + 2
  a, b = 1, 2
  1 > 2 ? true : false; puts "Hi"
  [1, 2, 3].each { |e| puts e }
```
- No spaces after (, [ or before ], ).
```ruby
some(arg).other
[1, 2, 3].length
```
- Use empty lines between defs and to break up a method into logical paragraphs.
- Use {...} for single-line blocks. Use do..end for multi-line blocks.
- Use CamelCase for classes and modules, snake_case for variables and methods, SCREAMING_SNAKE_CASE for constants.
- Prefer double quotes for strings.-
- Use def self.method to define singleton methods. This makes the methods more resistant to refactoring.
- Indent private and protected methods at the same column as the public methods. Just leave one blank line separating them.


----------------------------------------------

#Syntax
- Use each, not for, for iteration. (unless you know exactly what you are doing!)
- Indent when as deep as case. Do the same for if and else as well. Use the same style for arguments.
```ruby
this_is_an_example(first: 1,
                    second: 2)
```
- Use def with parentheses when there are arguments. Omit the parentheses when the method doesn't accept any arguments.
```ruby
 def some_method
    #do something
 end

 def some_method_with_arguments(arg1, arg2)
    #do something
 end
```
- Avoid the ternary operator (?:) except in cases where all expressions are extremely trivial. However, do use the ternary operator(?:) over if/then/else/end constructs for single line conditionals.
- Prefer && and || over and and or. ()
- Prefer ! over not.
- Prefer &:method_name to { |item| item.method_name } for simple method calls.
- Avoid return where not required.
- Prefer if/unless in single line instead using a block(with single-line body)
```ruby
# =(
if some_weird_condition
  do_something
end

# =D
do_something if some_weird_condition
```
- Don't use unless with else - It confuses everyone =P
```ruby
# =(
unless success?
  puts "failure"
else
  puts "success"
end

# =D
if success?
  puts "success"
else
  puts "failure"
end
```
- Use ||= freely to initialize variables. But DON'T do it to boolean variables.(because 'false' condition)
```ruby
name ||= "Chimene"
```
- Use _ for unused block parameters.
```ruby
# =(
result = hash.map { |k, v| v + 1 }
# =D
result = hash.map { |_, v| v + 1 }
```

- When defining class methods use def self.method if there isn't too many methods. If there's too much prefer using class << self. It's up to you when the change is necessary!

- Use implicit begin blocks.
```ruby
# =(
def method
  begin
    do_something
  rescue SomeCrazyError => e
    puts e
  end
end

# =D
def method
  do_something
rescue SomeCrazyError => e
  puts e
end
```

- Use the new hash syntax when using Ruby 1.9.
```ruby
# =(
h = { :names => 'Joaninha' }

#=D
h = { names: 'Joaninha' }
```


--------------------------------------------

#Naming

- Use snake_case for methods and variables.
- Use CamelCase for classes and modules.
- Use SCREAMING_SNAKE_CASE for other constants.
- Use ? suffix for predicate methods (the ones that return a boolean value).
```ruby
Array#empty?
```
--------------------------------------------

#Exceptions

--------------------------------------------

#Collections

--------------------------------------------

#Strings

-------------------------------------------

#Regular Expressions

------------------------------------------

#Percent Literals

------------------------------------------

#Keyword Arguments

-----------------------------------------

