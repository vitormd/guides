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
- Use ? suffix for predicate methods.
- Use CamelCase for classes and modules, snake_case for variables and methods, SCREAMING_SNAKE_CASE for constants.

----------------------------------------------

#Syntax
- Use each, not for, for iteration.
- Indent private methods at the same column as the public methods.
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
- Prefer && and || over and and or.
- Prefer ! over not.
- Prefer &:method_name to { |item| item.method_name } for simple method calls.
- Avoid return where not required.
