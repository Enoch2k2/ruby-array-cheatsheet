# Ruby Array Cheatsheet

### How to create a new array
```
array = []
```
alternatively
```
array = Array.new
```
### How to add to the end of an array
```
array.push(What we want to add to the end of the array)
```
Example:
```
array = ["green", "red", "blue"]
array.push("yellow")
# array now equals ["green", "red", "blue", "yellow"]
```

### How to add to the beginning of an array
```
array.unshift(What we want to add to the beginning of the array)
```
Example:
```
array = ["green", "red", "blue"]
array.unshift("yellow")
# array now equals ["yellow", "green", "red", "blue"]
```

### How to remove from the end of an array
```
array.pop
```
Example:
```
array = ["green", "red", "blue"]
array.pop
# array now equals ["green", "red"]
```

### How to remove from the beginning of an array
```
array.shift
```
Example:
```
array = ["green", "red", "blue"]
array.shift
# array now equals ["red", "blue"]
```

### How to access an element inside your array
```
array[What index position of that element you want to access]
```
Example:
```
array = ["green", "red", "blue"]
array[0] # gives us "green"
array[1] # gives us "red"
array[2] # gives us "blue"
```

### How to change an element at a given index
```
array[index] = new_value
```

Example:
```
array = ["green", "red", "blue"]

array[1] = "purple"

array # gives us back ["green", "purple", "blue"]
```

### How to check if an element exists in an array
```
array.include?(what you are searching for)
```

Example:
```
array = ["Bob", "Sarah", "Leah"]

array.include?("Charles") # gives us false
array.include?("Sarah") # gives us true
```

### How to check how many elements are in an array
```
array.length
array.size
array.count
```

Example:
```
array = ["Bob", "Sarah", "Leah"]

array.length # gives us 3
array.size # gives us 3
array.count # gives us 3
```

## Iterators

### each

We use each in order to loop through an array without worrying about what is returned by the each iterator
```
array.each do |element|
 # logic
end

array.each { |element| logic }
```

Example:
```
array = ["Bob", "Sarah", "Leah"]

array.each do |name|
  puts "Hello #{name}!"
end

# prints
Hello Bob!
Hello Sarah!
Hello Leah!
```

### map / collect

Map and collect are the same method we can call on arrays. We use map or collect in order to iterate through an array and return a modified array. Whatever is returned in the code block will be added into the new modified array.

```
array.map do |element|
  new_element_returned # the element here is soft returned using the same principals as methods, where the last thing is 
                       # returned
end
```

Example:
```
array = ["Bob", "Sarah", "Leah"]

array.map do |name|
  name.upcase
end # returns ["BOB", "SARAH", "LEAH"]

array # array remains ["Bob", "Sarah", "Leah"] since it's non destructive to our original array.
```

### find / detect

Find / Detect is the same method just like collect / map is the same method. We use find / detect in order to find an element based on a condition in the block. If the condition meets true, it will give us the first element that meets true as a return value, if the condition is never truthy, we will be given nil, meaning nothing was found.
```
array.find do |element|
  condition that meets truthy or falsy
end
```

Example:
```
array = ["Bob", "Sarah", "Leah"]

array.find do |name|
  name.include?("e")
end # returns "Leah"

array.find {|name| name.include?("z") } # returns nil
```

### select / find_all

Select / find_all once again is the same method with different names. We use these methods in order to find all of the elements where a condition in the code block that's returned is truthy, if no condition comes back as truthy, an empty array is given back.

```
array = ["Bob", "Sarah", "Leah"]

array.select do |name|
  name.include?("a")
end # returns ["Sarah", "Leah"]

array.select do |name|
  name.include?("z")
end # returns []
```

### how to add an index to our iterators (with_index)

Sometimes as you are iterating, you would like an index included with your iteration. In order to make this happen, you can use .with_index.
```
array.each.with_index do |element, index|
  # logic
end

array.map.with_index do |element, index|
  # logic
end
```

Example:

```
array = ["Bob", "Sarah", "Leah"]

array.each.with_index do |name, index|
  puts "#{index + 1}. #{name}"
end

# prints
1. Bob
2. Sarah
3. Leah
```

We can also offset the index value in order to clean up our code a little:

Example:
```
array = ["Bob", "Sarah", "Leah"]

array.each.with_index(1) do |name, list_number|
  puts "#{list_number}. #{name}"
end

# prints
1. Bob
2. Sarah
3. Leah
```

So here instead of having to do math in order to get 1, we can just tell with_index to add 1 to every index value.
