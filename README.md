# Ruby Instance Variable Modification Misunderstanding

This example showcases a common pitfall in Ruby when working with instance variables and accessor methods.  Directly modifying instance variables using `instance_variable_set` and `instance_variable_get` can lead to unexpected behavior if not handled carefully.  Improper usage can introduce subtle bugs that are difficult to track down. This repository highlights this issue and provides a correct solution.

## Bug Description

The code demonstrates that calling `my_object.value = 30` does not change the `@value` instance variable.   Attempting to modify an instance variable through the accessor method when no setter is defined (explicitly or implicitly by the Ruby interpreter) does not modify the instance variable's value. Direct access to `@value` through `instance_variable_set` is necessary to change the instance variable's internal value.

## Solution

The solution demonstrates that a setter method should be created to properly modify the instance variable's value. This ensures the intended side effects and data integrity when modifying object attributes.