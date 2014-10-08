---
layout: post
title: Grape strong parameters without Rails
---

{% gist jcarley/5703307 %}


{% highlight ruby %}
class FizzBuzz
  def self.evaluate(number)
    raise "Not a number" unless number.is_a? Integer
    return "fizzbuzz" if number % 5 == 0 && number % 3 == 0
    return "fizz" if number % 3 == 0
    return "buzz" if number % 5 == 0
    number.to_s
  end
end
{% endhighlight %}

