---
layout: post
title: Bottom to top approach for list comprehension
---

<div class="message">
  Howdy! This is an post talks about how best we could read list comprehension
</div>

With Referencing pull request comment [#809 (comment)](https://github.com/gunthercox/ChatterBot/pull/809#discussion_r125018676)

Yes, I agree with @gunthercox comment, readability is very important any language it will gives us many advantages for example

- Catching issues will be very easier and new develop/integration will become very easier.
- Etc.

Yes some-times it is necessary improve our code performance also, With some hacks the below formats are looking good to me.

The method i named it here :arrow_heading_up: **Bottom to top approach for list comprehension**, will provide more readability :eyes:

I did some exercise on some examples, All the example are valid PEP 8 Style Guide :thumbsup:

{% highlight python linenos %}
# Find the closest matching known statement
for statement in statement_list:
    confidence = self.compare_statements(input_statement, statement)

    if confidence > closest_match.confidence:
        statement.confidence = confidence
        closest_match = statement
{% endhighlight %}

vs

{% highlight python linenos %}
# The bottom to top approach for list comprehension, gives more readability
closest_match_and_confidence = [
    [
        statement,
        self.compare_statements(input_statement, statement)
    ] for statement in statement_list
]
{% endhighlight %}

Some more examples ...

{% highlight python linenos %}
for statement in statement_list:
    for response in statement.in_response_to:
        responses.add(response.text)
{% endhighlight %}

vs

{% highlight python linenos %}
# The bottom to top approach for list comprehension, gives more readability
[
    responses.add(response.text)
    for statement in statement_list
    for response in statement.in_response_to
]
{% endhighlight %}

-----

Send an <a href="mailto:malli.kv2@gmail.com?subject=POST:%20Bottom%20to%20top%20approach%20for%20list%20comprehension">Eamil</a> if you any have comments/suggestions.

