---
title: How I Learned Elixir Overnight
author: Givi
pubDatetime: 2023-09-04T21:00
postSlug: how-I-learned-Elixir-overnight
featured: false
draft: false
tags:
  - elixir
  - performance
  - python
  - css
  - design-system
description: This is the example description of the example post.
---

Typically, when seeking assistance or feedback from fellow programmers, it's advisable to begin by presenting the core problem rather than listing the attempted solutions. Unfortunately, this practice is not always followed. My journey began much the same way, with a deluge of ideas and solutions that ultimately unveiled a substantial CSS size issue.

Prior to the rise of Tailwind and the increasing popularity of BEM, a teammate responsible for styling our application embarked on a venture to establish a bespoke design system using SASS. This undertaking involved the creation of an extensive array of variables, mixins, and functions, culminating in the birth of a versatile design system. This system allowed our fellow markup developers to require minimal CSS code, as everything was managed through classes. However, a glaring problem emerged during the build phase: we were unable to eliminate unnecessary classes, resulting in an excessively large CSS file – a veritable behemoth.

To address this challenge, I embarked on a solution involving the development of a Python script designed to eliminate surplus CSS and incorporate it into our pipeline. To ensure its effectiveness, the script had to handle a range of complex scenarios:

1. **Class Name Parsing**: Initially, the script had to scour the entire application for class name usage. Although we had a naming convention in place, there were instances of non-conventional class names. Consequently, I had to resort to cumbersome regular expressions to cover all possible cases. This search extended across JSON files, TypeScript files, and Angular templates. Additionally, we encountered dynamic class names in TypeScript that also needed to be accounted for.
2. **External JSON Files**: The application contained class names within external static JSON files. To integrate these, the script had to download and parse these files, ensuring that they remained up-to-date.
3. **Market Distinction**: Our application was divided into two segments: one for the Georgian market and the other for the Armenian market. It was imperative to differentiate between the classes used in each segment and generate two separate minified CSS files. Moreover, these segments had distinct sets of static files, as mentioned earlier.
4. **CSS Parsing**: The final step involved parsing the entire CSS codebase, identifying all matches, and generating a minified version without any duplicates.

**_Python was slow_**. With a team of around 15 developers and frequent merge requests and pipeline runs, the script's execution speed proved to be a bottleneck, impeding our development workflow.

So, I had this crazy idea. Why was I even trying to make this Python script faster when it wasn't bringing me any joy? That's when I thought, "Hey, why not give Elixir a shot?" Elixir is built on top of Erlang, and with it, I could scale this script to work in parallel. Plus, it's a functional programming language, which for me, is like a match made in heaven.

I dove headfirst into learning Elixir, all in the name of making this CSS optimization thing work. And you know what? The syntax was a breeze to learn and understand. Creating new processes? Even easier. I pulled an all-nighter with Elixir, and the results were mind-blowing. When the external files were cached, the script was taking only 10 seconds to run. Can you believe it?

Here's how I made the magic happen:

1. I went all-in on parallel processing. I was parsing everything in parallel while simultaneously downloading every JSON file, which were also cached. Talk about multitasking!
2. Once I had the parsing results and the JSON files, I kicked it up a notch. I parsed every JSON file in parallel and added them to the results. It was like a symphony of efficiency.
3. For the grand finale, I compiled two separate CSS files in parallel from our main CSS files. The best part? It all depended on the results from the parsing. It was like the script had a mind of its own!

Moving from Python to Elixir was hands down the smartest decision I could've made, and here's why:

1. **Functional Programming**: Elixir is all about that functional programming life. It's like it encourages you to write code that's more predictable and easier to maintain. And let's be real, functional programming is just plain cool and expressive. It's like art for developers.

2. **Concurrency and Parallelism**: Elixir and Erlang? They're like the dynamic duo of concurrency and parallelism. With Elixir's lightweight processes and the actor model, I could scale my script to work in parallel like a boss. It was like having a team of coding ninjas at my fingertips, processing multiple tasks at once. The performance boost was unreal.

3. **Syntax and Ease of Use**: I mentioned it before, but it's worth saying again. Elixir's syntax is so easy to learn and understand, it's almost ridiculous. It's like the language was designed to make developers happy. Writing code in Elixir is like having a conversation with your computer, and it actually listens!

The optimized process using Elixir? It's like poetry in motion:

1. Parsing everything in parallel is like having a bunch of clever robots working for you, maximizing CPU usage and slashing parsing time like it's nothing.
2. Downloading and caching external JSON files in parallel? It's like having a personal assistant that knows exactly what you need before you even ask for it. I/O operations? What I/O operations?
3. Parsing JSON files in parallel after getting the parsing results and downloaded files? It's like having a team of data detectives that can extract information faster than you can say "optimization."
4. Compiling two separate CSS files in parallel based on the parsing results? It's like having a styling wizard that can generate optimized CSS files for different market segments with a flick of a wand.

And the result? A mind-blowing 10-second execution time with caching. That's like going from a horse and buggy to a rocket ship. Elixir's concurrency model is no joke, and parallel processing is its superpower.

Learning Elixir and using it to solve real-world problems like CSS optimization? It's like finding a cheat code for your coding skills. Not only do you get to expand your programming horizons, but you also get to experience the joy of functional programming and the rush of concurrency. And the best part? Your codebase will thank you for it, with better performance and maintainability that'll make you feel like a coding rockstar.
