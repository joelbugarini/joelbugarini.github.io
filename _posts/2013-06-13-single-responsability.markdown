---
layout: post
title:  "Think in a Single Responsibility Design"
date:   2013-06-13 23:20:51
categories: solid oop
---

Sometimes, designing a new app, modifying an algorithm or any other kind of software might be a hard thing to do. And talking about [Object Oriented Programming][oop], the design is essential for avoiding this issue. **Single Responsibility** is a principle that you can follow for make better Software Designs. [Robert C. Martin][robert] says:

“There should never be more than one reason for a class to change.”

A class with just one reason to be, a method with just one function and a variable declared just with one propose. This will help to make cleaner code and maintain it easily.

Here, a draw for make my point:

![My helpful screenshot]({{ site.url }}/assets/srd.png)

As you can see, in the good design a student have just one reason to be, “Study” and the teacher “Teach” and each one had some methods with one function. In this case, we are following the Single Responsibility Principle.

Applying this principle to code, it should be something like this:

Without SR principle:

{% highlight csharp %}
public class Student
{
    public string Study()
    {
        string Name;
        //Functions for study
        string Knowledge;
        // Answer questions in homework
        int Answers;
        // Design test
        string Test;
        // Answer test in a hour
        string answeredTest;
        // Teach class
        string speach;
        // Answer test in a hour
        string notes;
    }
 
}
{% endhighlight %}

With SR principle:


{% highlight csharp %}
public class Student
{
    private string Name;
 
    public string Study()
    {
        //functions for study
        return Knowledge;
    }
 
    public string DoHomework(string Questions)
    {
        // Answer questions in homework
        return Answers;
    }
 
    public void SolveExam(string Test)
    {
        // Answer test in a hour
        return answeredTest;
    }
 
    public void TakeClass(string Speach)
    {
        // Answer test in a hour
        return notes;
    }
}
{% endhighlight %}

As you can see, we are not summarizing nothing, in fact this generally make more lines of code, but also make our code more beautiful and clear. That’s the reason why we use it.

Now, rush into the class that have been giving you problems and apply the SRP, show it who’s the boss. As soon as you go deep with that class, you will understand it better and it will be easy to remember.

The Single Responsibility Principle is one of the five first principles of the [Object Oriented Programming][oop], identified by [Robert C. Martin][robert], and it is usually called S.O.L.I.D.

If you want more info about the topic, this links will help you:

[The S.O.L.I.D. Object Oriented Programming(OOP) Principles][solid]

Thanks for reading and have a nice day!

[oop]: https://en.wikipedia.org/wiki/Object-oriented_programming
[robert]: https://en.wikipedia.org/wiki/Robert_Cecil_Martin
[solid]: https://www.blackwasp.co.uk/SOLID.aspx
[remondo]: https://www.remondo.net/category/solid-series/
