# Intro to Hashes

## Learning Goals

+ Explain that hashes are useful to store unordered data
+ Use a hash to store unordered data
+ Use bracket notation to access values in a hash
+ Describe the advantages of using symbols for hash keys

## Lesson

+ Hi folks, this is Ian from Flatiron School. In this video, we're going to look at using hashes. Our learning goals for this video:
  + We'll look at why hashes can be useful in programming.
  + We'll use a hash to store unordered data
  + We'll use bracket notation to access values in a hash
  + And we'll talk about why to use symbols as hash keys in Ruby
+ So let's get started. We've seen that arrays can be really useful for storing lists of data, say, a list of names.
```ruby
names = ["Katherine", "Dorothy", "Mary"]
```
+ Sometimes, though, you might want to group data together, and each of the pieces of data might be slightly different. Say you're trying to group together data about a person. Some attributes you might have are name, age, and hometown. You could group this together using an array
```ruby
person = ["Ian", 99, "Pittsburgh, PA"]
```
+ So, there's a problem here. If another developer looks at this code, they have to kind of guess at what each of these things are. This gets even more complicated if we add more attributes - say, current city.
```ruby
person = ["Ian", 99, "Pittsburgh, PA", "New York, NY"]
```
+ Now, you really can't tell what the difference between Pittsburgh and New York in this example.
+ Luckily, there's a better way. We can use a hash. A hash works similarly to an array, but instead of the values being stored by index number, they're stored by key-value pairs.
+ The keys can be anything we want, but typically we'll use either a string or a symbol.
+ The syntax to create a hash literal looks similar to an array as well - instead of using square bracket, we use curly brackets, I sometimes call them mustache brackets for fun. This code creates an empty hash and assigns it to a variable.
```ruby
person = {}
```
+ Let's take our person array above and convert it into a hash. You can imagine our person array in sort of a table right now, by the index number.
+ At the 0 index, we have "Ian". At 1, we have 99. At 2, we have "Pittsburgh, PA", and at 3 we have "New York, NY"

| Index      | Value |
| ----------- | ----------- |
| 0      | Ian       |
| 1   | 99        |
| 2     | Pittsburgh, PA       |
| 3   | New York, NY     |

+ Let's replace the index numbers here with descriptive keys instead.
+ Let's use `name`, `age`, `hometown`, and `current_location` respectively

| Index      | Value |
| ----------- | ----------- |
| name      | Ian       |
| age   | 99        |
| hometown     | Pittsburgh, PA       |
| current_location  | New York, NY     |

+ This is how our hash will be organized. We can simply add those pairs when we create our hash now. I'll pair these up using the hashrocket symbol - an equals sign followed by a greater-than sign
```ruby
person = { "name" => "Ian", "age" => 99, "hometown" => "Pittsburgh, PA", "current_location" => "New York, NY"}
```
+ That's already much more clear. Here, I'm using strings as keys to my hash, and I can use any data type I want to, but I think symbols are actually a better choice.
+ For one thing, symbols are unique in Ruby, so they are a bit more performant.
```ruby
person = { :name => "Ian", :age => 99, :hometown => "Pittsburgh, PA", :current_location => "New York, NY"}
```
+ Also, when using symbols, I can use a bit of a shorthand syntax and write the colon at the end of the symbol instead of the hashrocket, like so:
```ruby
person = { name: "Ian", age: 99, hometown: "Pittsburgh, PA", current_location: "New York, NY"}
```
+ Either is totally valid, I tend to use the second because I find it a bit easier to type.
+ Cool, so now we've created our hash, let's look at reading and writing data to it.
+ So to read data our, I can use the bracket notation, just like an array. Only, instead of passing through the index number, I pass the key.
```ruby
person[:name] #=> "Ian"
person[:age] #=> 99
```
+ By default, if I look up a value that's not there, we'll get a nil value.
```ruby
person[:something_else] #=> nil
```
+ I can add data to the hash or change any value by using an equals sign. So the syntax is hash_name - bracket key bracket equals value.
```ruby
person[:age] = 100
person[:favorite_food] = "Pasta"
```
+ If I look at my hash now, I can see we've added updated both of those values.
+ If I want to check if a hash contains a certain property, I can use the `has_key?` method like this:
```ruby
person.has_key?(:dog) #=> false
person.has_key?(:name) #=> true
```
+ Finally, if I want to just entirely delete a key from a hash, I can use the delete method like this:
```ruby
person.delete(:age)
```
+ And we can see we've now removed the age from our person.
+ So that's a quick intro to hashes. Just to recap what we've learned:
+ We looked at why hashes can be useful in programming. Mainly to group related data together. There are some other uses too that we can look at in the future.
+ We used a hash to store unordered data about a person
+ We used bracket notation to access and overwrite values in a hash
+ And we also talked about why to use symbols as hash keys in Ruby, and looked at the different syntax for that.
+ Thanks so much for watching - happy coding! 
