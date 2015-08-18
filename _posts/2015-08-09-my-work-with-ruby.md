---
layout: post
title: "My Work With Ruby"
date: 2015-08-09 20:59:36
author: Nayyir Jutha
summary: Showcasing basic starter projects for learning the programming language Ruby. 
categories: jekyll
thumbnail: heart
tags:
 - work
 - with
 - ruby
---


##FizzBuzz

{% highlight ruby %}
def fizzbuzz(low, high)
  num1.upto(num2) do |i|
    if i % 5 == 0 && i % 3 == 0
      puts "FizzBuzz"
    elsif i % 5 == 0
      puts "Buzz"
    elsif i % 3 == 0
      puts "Fizz"
    else
      puts i
    end
  end
end
#=> prints the numbers within the given range.
#=> the program subsitutes multiples of 3 with "Fizz",
#=> multiples of 5 with "Buzz" and multiples of both
#=> with "FizzBuzz" to STDOUT
{% endhighlight %}

The generic fizzbuzz was definitely the proper first project to complete whilst on my journey to learn Ruby. The idea of fizzbuzz incorporates the necessary logic and arithmetic skills needed to be a prominent developer, and is an exceptional exercise for those willing to learn. You can view the rest of this exercise from this [Github Gist](https://gist.github.com/6bc87e4bbc02f80807d8)

##Character Counter
{% highlight ruby %}
def count_letters(string)
  @letters = {}
  string.gsub(/\s+/, "").each_char do |letter| 
      unless @letters[letter] 
        @letters[letter] = 1
      else
        @letters[letter] += 1 
      end
  end
  @letters
end

puts count_letters("lighthouse in the house...")
#=> using regex to count the number of characters
#=> in a given string
{% endhighlight %}

The character counter is a basic representation of the use of regular expressions, RegEx for short, within that of generic ruby functions like **`gsub()`** Visit this [Gist on Github](https://gist.github.com/rh0delta/67b24342c9e4a10ba5e8) to view the rest of the project.

##Roman Numerals
{% highlight ruby %}
VALUES = [
  ["M", 1000],
  # ["CM", 900], 
  ["D", 500],
  # ["CD", 400,], 
  ["C", 100],
  # ["XC", 90], 
  ["L", 50],
  # ["XL", 40], 
  ["X", 10],
  # ["IX", 9], 
  ["V", 5],
  # ["IV", 4],
  ["I", 1] 
]

def to_roman(num)
  # Your code here
  roman = ""

  VALUES.each do |pair|
    letter = pair[0]
    value = pair[1]
    roman += letter*(num / value)
    num = num % value
  end
  return roman
end
{% endhighlight %}

This snippet consists of a function to convert a regular integer into its roman numerals equivalent.
With the removal of the comments, the progrm will display the modern representation of roman numerals aside
from the original format. Visit this [Gist](https://gist.github.com/rh0delta/2563fbb57085c7bdc1b6) to view the rest
of the project, including the function call.