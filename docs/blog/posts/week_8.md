---
date: 2024-07-19
categories: [Internship]
authors: [nangosha]
draft: false
---

# Week 8: Introduction to reflection - Part 1

I have always wondered if there was a way one could access the private members of a class, or even methods that are not exposed in a public API. That's how I landed on reflection.

<!-- more -->

Recently, I was(and still am) reading a book called **`Androids: The Team that Built the Android Operating System`**` by Chet Haase. It is about the Android OS, its conception, and how it has evolved to be the OS we know today. It goes into a lot of details about the decisions/tradeooffs that were taken, the marketing, acquisitions and many other interesting bits. The stories in the book are from the very people who built the system from the ground up!

The whole book was interesting and I could go on with the praise but my attention was particularly drawn to Chapter 15 which was about notifications in the Android OS. This chapter has stories from the designers of the notification service, how they approached this problem and how this idea of notifications proved to be a major factor in the success of the Android OS.

I am fully aware that Android provides an android framework as part of the Android SDK that developers can use to build applications on top of this operating system. One thing I have been interested in for a long time is how one can extend the functionality provided by the framework, or even override the APIs provided by this framework. The `NotificationManager` class would in my opinion be a good candidate for trying out my ideas. If only I could find a way of overriding its functionality to something like say, only showing a custom-coded notification message irrespective of the app, then  that would be a good start for me! 

I also thought about doing something disabling push notifications and only allow local ones, but I guess that would come on later. There was no need to get ahead of myself here! With my overzealous dreams specified, I proceeded to do some searching for anything that would draw me closer to what I wanted to achieve.


These are some of the possible approaches to my problem

- Extend the notifications class and override the public/protected methods inside your custom implementation.
- Access the source code of the class you are interested in and modify it.
- Use reflection(this is a new word, never heard of it!). This gives you ability to modify even the private methods of a class.

Reflection, was new to me(if I have heard of it before, then I completely forgot about it), so I decided to go down this rabbit hole and see what I could find.

## What is reflection?

To put is simply, reflection is a functionality that allows you to access/modify the the runtime behavior/properties of an application

## Possible use cases for reflection

These include but are not limited to:

- **Debuggers and test tools** - these use reflection to be able to access and examine the private members of a class as a program executes
- **Dependency injection** - Popular frameworks like Spring use reflection techniques to inspect components and their dependencies and then use dynamic proxies to inject those dependencies at runtime.
- **Dynamic method invocation** - This can allow you to retrieve the method name as a string and invoke that method dynamically.


## What are the dangers associated with using reflection?

- Reflection can tend to be slow, hence it is associated with performance problems for your application.
- It is normally very hacky, easily breaks across updates and also very hard to maintain.
- Reflection is normally considered an advanced topic and *"it should be used only by developers who have a strong grasp of the fundamentals of the language/framework"*
- More so than often, one could land into security issues when using reflection capabilities, since applications may run outside a restricted security context.

## Wrapping it all up

Reflection is a concept I am glad to be aware of right now and I can't wait to use it in one of my applications. Of course I will use it with caution, and only when I must!

## Disclaimer

For the scope of this blog post, I was not able to realise my desired goal of having a custom `NotificationsManager` implementation, but I think the things encountered during my research would form a good starting point for that effort. I will later release a new blog post with the custom implementation, or even update this very post.

I have also not included any code samples since I do not want this post to be very long(although this can be changed in the future).

## Important links for further reading

1. [Reflection with Kotlin](https://www.baeldung.com/kotlin/reflection)
2. [Java reflection API](https://docs.oracle.com/javase/tutorial/reflect/)
3. [Reflection as a tool to debug objects[Document]](https://inria.hal.science/hal-03846015/document#:~:text=Reflection%20is%20useful%20to%20build,program%20in%20a%20normal%20execution.)
4. [Introduction to reflection](https://proandroiddev.com/peeking-behind-the-forbidden-door-of-reflection-by-prafull-mishra-2293d3034e9f)
5. [FreeReflection library for Android](https://github.com/tiann/FreeReflection)

