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