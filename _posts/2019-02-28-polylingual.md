---
layout: post
title: "Branching Out into Other Languages"
date:   2019-02-28 21:15:18 -0700
categories: etymology
---

No software engineer who has been in the industry for more than 10 years has only learned one language.

Each language has its own tradeoffs and considerations.

Learning Ruby after you learned Python will have a lot more crossover than learning C++ after Python.

However, learning different languages exposes you to new ways of thinking about software.

Learning your first programming language goes hand in hand with learning how to program in general. When you start writing number guessing games and adventure text games, for you, programming is that language.

As you program more and develop a deeper understanding of what it means to program, sooner or later you'll write code in another language. You'll notice that some are more similar than others.

```python
print("Hello, world!")
```

```ruby
puts "Hello, world!"
```

but maybe you notice that `puts("Hello, world!")` works as well.

```javascript
console.log("Hello, world!");
```
Or maybe its `alert("Hello, world!")`

You check on your buddy and he says in C++, hello world looks like this

```c++
#include <iostream>
using namespace std;

int main()
{
    cout << "Hello, World!";
    return 0;
}
```

```go
package main

import "fmt"

func main() {
    fmt.Println("hello world")
}
```
## Complementary Languages
For example, Ruby and Go are near perfect compliments of each other. There's a lot that Ruby is great at, and I love Ruby on Rails. However, I'm fully aware that Ruby is awful at handling concurrency.

Go, on the other hand, was built with concurrency in mind.

How would I go about learning Go? Learning the syntax is the obvious start. I enjoy going to meetups as well, and I recently went to a Go meetup that was a workshop on building a simple API in Go.

Having worked with RoR and understanding the framework and underpinnings of what goes into an API, seeing it written in Go allowed me to focus on features unique to the language, such as slice headers and malloc.

One of the prominent criticisms I hear about Rails is that it's too much magic. I've worked in Sinatra and Express, but going through the process of making an API in Go truly showed me how much work Rails does under the hood for the developer.

## Grow as a Developer
This section may seem to be similar to Complementary Languages, and it is, but there are some differences. Discussing complementary languages shows how learning more than one language can cover any deficit you have in your developer skillset, while this focuses on learning more and improving the quality of your code in any language that you write in.

Linguists say that the language we speak and think in affects what we think and how we structure our thoughts. INSERT LINK TO LINGUSTS SAYING THIS -- MAYBE AN ARTICLE OR ACADEMIC JOURNAL THINGY

Why would programming languages be any different?

Knowing how to program in two languages demonstrates that you know what you're doing. You can separate the forest from the trees. You're not just another script kiddy; you understand what the program is doing on a conceptual level and are using the best tool at your disposal to create it.

## Marketability
Most of us write code to put food on the table, or aspire to, at least. We do this usually by getting a full time job or doing contract work. More languages opens up the market for the developer and exposes them to more opportunities. You may be a killer Rust developer, but if you can't apply your software skills into JavaScript or Java, your prospects may be limited.

I'm not saying that you should write "Hello, World!" in 100 different languages and put them all on your resume. Breadth is not the main metric to shoot for; however, a developer who only knows one language severely limits themselves on the job market. Even if they're interviewing for a job in their language, the company they're applying for almost certainly uses multiple other languages for their tech stack, and the hiring manager could prefer the developer who has experience with multiple languages in the tech stack.

Specialization in one area is desirable as well. A model that seems to have success is a T-shaped professional. A specialist in one area or language, but enough general knowledge and breadth to be of use in any area. Valve uses [this employee handbook](https://steamcdn-a.akamaihd.net/apps/valve/Valve_NewEmployeeHandbook.pdf)

## Tech Stacks
You can get by learning the fundamental concepts of computer science by programming your way through a language, but if you want to create a fully functioning piece of software, you're going to have to use multiple different languages to develop each part of the tech stack.

There are many tech stacks out there today that focus on a specific language (Ruby on Rails, Python/Django, Node/React), but even within those stacks, you'll have to learn how to interact with a database (most likely in SQL), how to process data on the backend, and then display the data to the user on the frontend(HTML/CSS/JS or some sort of framework).

Making a Ruby on Rails app at first glance appears to be only focused on one specific language. You interact with the database using Active Record, the backend is written in Ruby and Ruby on Rails helper methods, and you display the data using an .erb file, or embedded Ruby. However, Active Record is just a convenient shorthand for Ruby, and .erb files are essentially HTML that have some dynamic values, and then you're still writing CSS. Imagine if you're working on a Rails app, and they decide to move the frontend off of Rails, make the app into an API, and have a React frontend that connects to the APIs. Now you're wishing you had learned what .jsx was!
