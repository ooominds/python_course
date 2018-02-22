# Python Course Cheat Sheet

## What is this even?
```Python
type(item) # return type of item like str, int or list 
help(item) # show help file for item, especially useful to see function arguments
```

## Lists
Initialize a list:
```Python
my_list = list()
my_list = []

first_ten = [0,1,2,3,4,5,6,7,8,9]
first_ten = range(10)
next_ten = range(10, 20)
```
Add elements:
```Python
my_list.append(element)
new_list = old_list + other_list # concatenate old_list and other_list
my_list += other_list # add elements of other_list to my_list
```
Remove elements:
```Python
del my_list[index] # removes indexed element from my_list
my_list.remove(item) # removes first occurrence of item from my_list
item = my_list.pop() # removes first element from list and returns it
item = my_list.pop(index) # removes indexed element from list and returns it
```
Sort:
```Python
sorted_list = sorted(my_list)
my_list.sort() # sorts in-place, i.e. my_list is now sorted and no copy is returned

sorted_list_reverse = sorted(my_list, reverse=True)
my_list.reverse() # reverse sorts in-place

sorted_by_key = sorted(my_list, key=sorting_function) # sort by key
my_list.sort(key=sorting_function)
```
Access elements:
```Python
first_element = my_list[0] # counting starts at 0!
nth_element = my_list[n-1]
last_element = my_list[-1] # negative indices are accepted!
first_ten_elements = my_list[0:10] # in slicing, the indices refer to cut points before/after each element!

# can leave out start or end and all will be selected
first_ten_elements = my_list[:10]
all_but_first_two_elements = my_list[2:]
```
Iterate over elements:
```Python
for item in my_list:
  # do something with item
```
Check whether item is in list:
```Python
item in my_list # boolean expression, i.e. is True or False
```
Get number of elements in list:
```Python
my_list_length = len(my_list)
```

## Sets
Initialize a set:
```Python
my_set = set()
my_set = {}
```
Add elements:
```Python
my_set.add(element)
my_set.update(list_of_elements)
```
Combine sets:
```Python
union = my_set | other_set # union of my_set and other_set
union = my_set.union(other_set)
my_set.update(other_set) # union in-place, my_set now contains all elements

intersection = my_set & other_set # intersection of my_set and other_set
intersection = my_set.intersect(other_set)
my_set.intersection_update(other_set) # in-place intersection
```
Remove elements:
```Python
my_set.discardd(item) # removes item from my_set
my_set.remove(item) # removes item from my_set, throws an error if item is not found
item = my_set.pop() # removes random item from set and stores it in item

difference = my_set.difference(other_set) # returns items in my_set but not in other_set
my_set.difference_update(other_set) # removes items in other_set from my_set in-place
```


## Dictionaries
Initialize a dict:
```Python
my_dict = dict()
my_dict = dict(list_of_pairs)
```
Add element:
```Python
my_dict[key] = value
```
Retrieve value:
```Python
value = my_dict[key] # throws an error if key does not exist
value = my_dict.get(key) # returns None if key is not found
value = my_dict.get(key, some_value) # returns some_value if key is not found
```
Iterate over keys:
```Python
for key in my_dict:
  # do something
```
Iterate over key-value pairs:
```Python
for key, value in my_dict.items():
  # do something
```
Iterate over values:
```Python
for value in my_dict.values():
  # do something
```
Remove item:
```Python
del my_dict[key]

# remove all keys satisfying a certain condition
for key in my_dict.iterkeys(): # iterkeys() allows to remove keys while iterating over them
  if some_condition:
    del my_dict[key]
```

## Strings
Strings are basically lists as well (each character is one element), so the list methods will mostly apply too!

Change case:
```Python
string_lower = my_string.lower()
string_upper = my_string.upper()
string_toggle = my_string.swapcase()
```
Split on symbol:
```Python
my_string_list = my_string.split(separator)
tab_separated_elements = my_string.split("\t")
```
Join multiple strings into one:
```Python
my_string = first_string + second_string

list_of_strings = ["Here","be","dragons","..."]
my_string = " ".join(list_of_strings) # join list placing " " in between them
```
Remove trailing/leading symbols:
```Python
my_string_clean = my_string.strip() # removes whitespaces, newlines and tabs
my_string_no_linebreak = my_string.strip("\n") # removes newlines
```
Match beginning/end of string:
```Python
my_string.startswith(some_string) # boolean, True if my_string begins with some_string
my_string.endswith(some_string)
```
Turn something into a string:
```Python
five_string = str(5) # 5 is integer, five_string is str
```

## File Access
Open file:
```Python
my_input_file = open(file="Path/to/file", mode="r") # open file for reading (is default anyway)
my_input_file = open(file="Path/to/file", encoding="utf-8") # open file for reading, specify encoding
my_output_file = open(file="Pat/to/otherfile", mode="w") # open file for writing
```
Read/Write to file:
```Python
next_line = my_file.readline()
all_lines = my_file.readlines()
my_file.write(string_to_write)
my_file.writelines(list_of_strings_to_write)
```
Start reading/writing at position (in bytes):
```Python
my_file.seek(0) # go back to beginning of file
```
Close an opened file:
```Python
my_file.close() # makes sure everything written to it is actually saved to disk!
```

## Control Flow
Execute on condition:
```Python
if condition:
  # do something if condition is True
elif other_condition:
  # do something if condition is False and other_condition is True
else:
  # do something if condition is False and other_condition is False
```
Execute a number of times:
```Python
for _ in range(number_of_times):
  # do something
```
Repeat execution as long as condition holds:
```Python
while condition:
  # do something
```
Exit loop at any point:
```Python
for item in collection:
  # do something
  if condition:
    break # break out of for loop on condition

while condition:
  # do something
  if other_condition:
    break # break out of while loop on other_condition
```
Do something only if a for loop completes normally:
```Python
for item in my_list:
  # do something with each item
  if condition:
    break
else:
  # do something in case a break occurred (i.e. if condition was true for some item)
```

## Functions
Define a function:
```Python
def my_function(first_argument, second_argument=4):
  # do something with arguments
  # store in result
  return result
```
Call a function:
```Python
result_with_3 = my_function(first_argument=1, second_argument=3)
result_with_4 = my_function(first_argument=1) # second_argument is 4 by default in definition above!
result_with_5 = my_function(1, 5) # feed arguments by position in definition, without keyword
```

## Regular Expressions
Compile regular expression:
```Python
import re
my_regular_expression = re.compile("somePattern")
```
Search string for pattern
```Python
my_regular_expression.search(some_string):
```

## Idioms
Execute if item is not 0 or None:
```Python
if item:
  # do something
```
Increase variable in place:
```Python
some_number += 1 # add one to some_number
```

## Various
Imports:
```Python
import package # import full package
from package import module # imports module from package
from package import module as mod # imports module from package and assigns it the name "mod"
from package.subpackage import module # import module from subpackage of package
```
