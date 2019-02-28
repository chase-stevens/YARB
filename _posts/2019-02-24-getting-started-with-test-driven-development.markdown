---
layout: post
title:  "Getting Started with Test Driven Development"
date:   2019-02-23 21:15:18 -0700
categories: testing
---
Test Driven Development is considered to be a best practice in the software industry, yet many teams ship code without tests.

## What it is
Test Driven Development, or TDD, is a method of creating software by writing tests before writing code.

[Uncle Bob](https://www.youtube.com/watch?v=qkblc5WRn-U) describes TDD with three rules:
* You are not allowed to write any production code unless it is to make a failing unit test pass.
* You are not allowed to write any more of a unit test than is sufficient to fail; and compilation failures are failures.
* You are not allowed to write any more production code than is sufficient to pass the one failing unit test.

It may seem unintuitive to write tests for code that doesn't exist yet; however, by writing tests first, we ensure we have a clear expectation of what our code will do, and we also guarantee that we don’t procrastinate and table writing tests until it’s too late.

While it may seem easier to jot down whatever code comes to mind and hack your code together until the compiler runs, you’ll end up spending more time me debugging your hastily written code than you would writing tests, which leads to substandard code and, even worse, you don't have any tests written for the future.

Tests may not be necessary for small projects or coding exercises, but for maintaining the health and stability of your programs and projects for the foreseeable future, test driven development is the way to go.

## Why it matters
Some people take test writing so seriously that they adopt the mantra “If it’s not tested, it’s broken.”

Test Driven Development helps immensely with debugging and cuts down on time that would be spent hunting down bugs.

One benefit of writing tests first is that they don’t get lost in the shuffle. Say you’re on a tight deadline and as a time saving measure, you skip writing tests. You ship the new feature and then you’re back to the grindstone, with the same deadline, having to cut testing from your development. Soon, you’ve shipped an entire codebase with buggy code and no tests!

By using test driven development and writing the tests first,

## How to implement it
Many programming languages have libraries and frameworks for testing. JavaScript has [Jest](https://jestjs.io/) and [Mocha](https://mochajs.org/). Ruby has [rspec](http://rspec.info/). Python has built in test modules as well as Pytest (https://docs.pytest.org/en/latest/). Java has JUnit (https://junit.org/junit5/) -- if it’s a programming language, it probably has a test framework.

No matter what type of framework you choose, you’ll write a test that has an expected outcome. If your expected outcome or assertion evaluates to true, then the test is passing. If it is false, then the test is considered failing.

Let’s take a look at two tests for creating a url object in a url shortening web application built in Ruby on Rails.

```ruby
require 'test_helper'

class UrlsControllerTest < ActionDispatch::IntegrationTest
  test "should create a new url" do
    url = Url.new
    assert url.save
  end

  test "should only save a unique url" do
    url = Url.new
    url.text = "https://www.amazon.com/Ruby-Under-Microscope-Illustrated-Internals/dp/1593275277"
    assert_not url.save, "Saved a duplicated URL"
  end
end
```

Here we have two tests, test "should create a new url" and test "should retrieve an existing url."

The first test creates a new url object and then asserts that we can save the url to the database. Ruby evaluates a successful completion of the save method on the url object and returns true, this the assertion is a success.

The second test makes sure that we only save urls that are unique -- if the url already exists in our database, we would rather refer the user to the existing url object. However, instead of checking against data in our actual database, we create dummy data in what's called a test fixture.

The purpose of a test fixture is to make sure we have a standard environment in which tests are run so that results are repeatable.

Here we have an object in our urls.yml file with which we can test our code against.

```ruby
ruby_book_page:
  text: https://www.amazon.com/Ruby-Under-Microscope-Illustrated-Internals/dp/1593275277
  short: f0r
```
Since this object is in the urls.yml file, our code treats it as an existing url object in our database. Our code creates a new url, assigns the Amazon link to the text property, and when the save is unsuccessful and returns false, our assert_not test is a success.

Without any validation, the url would be saved and our test would fail. We then add our code to our url model that will validate each url and only accept unique urls.

```ruby
class Url < ApplicationRecord
  validates :text, uniqueness: true
end

```

We then run our tests again and see that it's passing, thus completing the process of test driven development (for that line of code, anyway).

There are a ton of different  methods and ways to test your code -- hopefully, this helps you take a step in the right direction.
