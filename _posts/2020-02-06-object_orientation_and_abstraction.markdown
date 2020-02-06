---
layout: post
title:      "Object Orientation and Abstraction"
date:       2020-02-06 21:26:17 +0000
permalink:  object_orientation_and_abstraction
---


What is abstraction? Abstraction can be defined as 
"the quality of dealing with ideas rather than events." (https://www.google.com/search?q=abstraction&oq=abstraction&aqs=chrome..69i57j0l7.2463j1j7&sourceid=chrome&ie=UTF-8)

Abstraction is an important concept to understand as a programmer and equally to understand in everyday life as well. The reason abstraction is so important is very simple - **it can make our lives so much easier.**

When beginning to learn any new concept, language, subject, etc., we always begin with the bare basics. In the case of Software Engineering, we begin with learning simple concepts like datatypes, using conditional statements, and interpolation.

Object Orientation is a layer of abstraction. We are taking what we have learned about data types and methods that manipulate them and taking it up one level of abstraction and using them on objects of classes. When we are first taught what a string is, the concept of it being its own class is probably rather foreign to someone with no coding background. This concept becomes more clear as we dive into creating our own classes.

Let's start with Procedural Ruby. The curriculum may have a test that requires you to build a method called `full_name` that accepts the arguments of someone's first and last name, and returns them as a single string. That method would look something like:

```
def full_name(first_name, last_name)
  "#{first_name}" + "#{last_name}"
end
```

So now, when you call the method `full_name("Cody", "Dupuis")` it returns my full name! 

Now, in the sense of Object Oriented programming, we would have this method inside of a class instead. Let's say we have a person class:

```
class Person
attr_accessor :first_name, :last_name

def full_name(first_name, last_name)
  "#{first_name}" + "#{last_name}"
end  
	  
end
```

Now we can instantiate a Person object like `cody = Person.new("Cody", "Dupuis")`, and thanks to our `attr_accessor` macros, it sets the first and last name when instantiated. We can access these methods as so:
```
cody.first_name #=> "Cody"
cody.last_name #=> "Dupuis"
```

And since we defined our method `full_name`, we can do
```
cody.full_name #=> "Cody Dupuis"
```



