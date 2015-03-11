#**Minitest**

MiniTest is simple and pure ruby! Therefore, same good practices aply.


##Coding Style, Basic Sintax and Naming

Refer to our [ruby style guide](https://github.com/BankFacil/guides/tree/master/style/ruby).

## Running

```ruby
# To run all tests 
$ rake test

# To run all tests in a specific folder
$ rake test test\folder\

# To run all tests in a specific class
$ rake test test\path\class_name_test.rb

# To run a specific test
# eg.
# test 'the truth'
#   assert true
# end
$ rake test test\path\class_name_test.rb test_the_truth
```
Alternatively, to run a specific test, you can use `focus` before the tests you want so only the ones with `focus` will run.

```ruby
focus
test 'the truth 1'
  assert true
end

test 'the truth 2'
  assert true
end

# In this case, only test_the_truth_1 will run
```
##Sintax

* **Do not forget** to include test_helper;
* The name of the test class is the class name followed by Test (in CamelCase);
* Each test starts with the word "test", followed by quote marks with the name of the method that is being tested and its conditions;
* Each test is written within `test/`, following a similar path as the path of the class that is being tested;
* Use `setup` to define what you will need to use before each test (similar to `before :each` from *RSpec*);
* Use `teardown` to define what you will need to use before each test (similar to `after :each` from *RSpec*);

```ruby
# test/class_path/class_name_test.rb
# test for app/class_path/class_name.rb

include 'test_helper'

class ClassNameTest

  def setup
    # called before every single test
  end
  
  def teardown
    # called after every single test
  end

  test "method_name <when conditions>"
    # tests something
  end

end
```

MiniTest uses assertions to evaluate an object [or expression] for expected results.

- Check [Rails Guides](http://guides.rubyonrails.org/testing.html#available-assertions) and [MiniTest documentation](http://ruby-doc.org/stdlib-2.0/libdoc/minitest/rdoc/MiniTest/Assertions.html) for lists of the available assertions. 

##test_helper

The test_helper.rb specifies the default configuration to run your tests. You can also use it to define helper methods that can be used to all tests.

##Fixtures

>Fixtures is a fancy word for sample data. Fixtures allow you to populate your testing database with predefined data before your tests run. Fixtures are database independent written in YAML. There is one file per model.<br>
>-- *Rails Style Guides*

```ruby
# in test/fixtures
# models.yml (model name in plural)

model_one:
 property_one: value_one
 property_two: value_two

model_two:
# ...
```

For associations, you can define a reference node between two fixtures.

```ruby
# Example taken from Rails Guides

# in fixtures/categories.yml
about:
  name: About
 
# in fixtures/articles.yml
one:
  title: Welcome to Rails!
  body: Hello world!
  category: about
```

Fixtures are ActiveRecord instances, so you can access them directly.

```ruby
# test/class_path/class_name_test.rb

# this will return Article object for the fixtures named one
articles(:one)

# this will return the property title for one  
articles(:one).title
 
# you can also access methods available on the Article class
articles(:one).articles_method
```