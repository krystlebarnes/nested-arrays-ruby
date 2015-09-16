# Multidimensional Arrays 

## Objectives

1. Create nested, or multidimensional, arrays.
2. Read data from a nested array.
3. Write data to a nested array.
4. Iterate over a nested array.

## What is a Nested Array?

An array is like a list but in code form. It is a way for your program to store pieces of data as a collection. Arrays can contain any data types in any combination––strings, integers, even other collections like arrays and hashes. 

Arrays are declared by listing variable names or literals separated by commas (,) and wrapped in square brackets []. For example:

```ruby
students = ["Mike", "Tim", "Monique"]
```
We know that arrays can contain any type of data, even other arrays. Let's see that in action: 

```ruby
nested_students = [["Mike", "Grade 10", "A average"], ["Tim", "Grade 10", "C average"], ["Monique", "Grade 10", "B Average"]]
```
A nested, or multidimensional array, is an array whose individual elements are also arrays. 

## Why Use a Nested Array?

Nested arrays are useufl for storing groups of similar data. One example of nested array usages comes to use from the Google Maps API. Google Maps provides a Javascript function that you, the developer, can use to add Google Maps to your own website. Don't worry about Javascript right now, just understand that a Javascript function is like a Ruby method. 

The map-making function (or method, as we're going to think of it) was designed to take in an argument of a nested array––an array in which each index element is an array that contains a place name, latitude and longitude. In other words, something that looks like this:

```ruby
location_array =  [["The Flatiron School", 40.705329, -74.013970], ["Disney World", 28.385233, -81.563874]]
```
## Reading and Writing With Nested Arrays

### Accessing Data From a Nested Array

To access data from and add data to (i.e. "read and write") with a nested array, we can use the same methods we've been using to deal with one-dimensional arrays. 

Let's stick with our `students` and `nested_students` arrays for now. To grab an element out of the `students` array, we used bracket notation, plus the index number of the elemenet we want. 

```ruby
students = ["Mike", "Tim", "Monique"]
students[0]
  => "Mike"
``` 
To access the same student's name from our `nested_students` array, we use bracket notation to drill down into the level of the array we want to access.

```ruby
nested_students = [["Mike", "Grade 10", "A average"], ["Tim", "Grade 10", "C average"], ["Monique", "Grade 11", "B average"]

nested_students[0][0]
  => "Mike"
```
The first set of brackets refers to the top-level of the array––the array that contains all of the other arrays. 

```ruby
nested_students[0]
  => ["Mike", "Grade 10", "A average"]
```
We can see that the return value of `nested_students[0]` is the element at index 0 of the nested_students array. That element happens to be an array that looks like this:

```ruby
["Mike", "Grade 10", "A average"]
```

If you set the return value of calling `nested_students[0]` equal to a variable, we can then operate on it with further bracket notation:

```ruby
mike = nested_students[0]
mike[0]
  => "Mike"
```

The syntax that we used earlier on: `nested_students[0][0]` is simply the chaining of method calls––we are calling the `[]` method on the return value of calling the `[]` method on `nested_students`. 

Let's try that again. This time, let's write a line of code that returns the grade level of the last student in the `nested_students` array. Give it a shot in IRB yourself before reading on. 

```ruby
nested_students[2][1]
  => "Grade 11"
```

We are accessing the element at index 2 of the `nested_students` array, which is the last element in that array. That element happens to be an array with three index elements, the second of which (the element at index 1) is the grade level of the student. So, `nested_students[2]` grabs us the array that describes the last student in the list, and chaining on `[1]` grabs the value of the element at index 1 of *that* array––the string `"Grade 11"`.

Now that we are getting comfortable getting data *out* of a nested array, let's work on adding data *to* such an array. 

### Adding Data to a Nested Array 

## Outline

1. Remind them about arrays. Arrays in ruby can contain objects of any type. Including even other arrays entirely.
2. A simple nested structure, an array within an array. Sort of pointless, but shows structure.
3. Demonstrate reading and writing with that simple nested array.
4. Real world nested arrays.
  - Example of structure, why nested is better
  - Example of reading and writing

5. Iterating of nested arrays
  - use real array examples and show how you'd iterate to deconstruct them.
  - read / write data into the inner arrays
  - iterate over the inner arrays themselves with a nested loop.

6. Complext nested arrays, 3-4 deep.
  - structure, reasoning
  - reading/writing/iteration (quick examples)
  - danger / not good to go past 3