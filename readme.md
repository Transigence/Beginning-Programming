# Beginning Programming
>‟Programs must be written for people to read, and only incidentally for machines to execute.”  
— H. Abelson and G. Sussman (in "The Structure and Interpretation of Computer Programs")
## Preface
Programming computers is not a beginner-friendly endeavor. Part of the reason why is that, unlike most other pursuits, there does not seem to be one clear beginning. There are many areas of knowledge that are needed to write programs, and most of these areas lean on at least a few of the others. This presents a bit of a paradox when it comes to creating a programming curriculum for yourself or another. No matter where you start, you are going to be lost for a little while. You are going to have questions to which you simply must defer answers for a while. There are just _no good ways_ to begin. Once you surrender to this fact, you can begin in earnest.

In order to begin, you must become a novice in six _core disciplines_ simultaneously. They are:
* Knowing the computing environment
* Competence with the toolchain
* Competence with the grammar and syntax
* Familiarity with the namespaces, libraries and/or modules
* Knowing programming fundamentals and information science
* Reading and understanding the documentation

Learning to code is a daunting task to the uninitiated. The purpose of this essay is to give the reader a general understanding of the lay of the land, so he or she can create a cirriculum sensibly without any undue frustration. A little bit of ignorance about any one of the core disciplines can add a lot of drag to the learning process. 

It will be necessary to periodically take time to better yourself in all six of these core disciplines, and to weave these periods of time together into a fabric that will form the basis of your progression as a software developer.

In the following chapters, I will describe to you _what_ these disciplines are, as well as why it is necessary for you to have a certain competence with them. Afterwards, I will cover a few other helpful topics that aren't directly related to the core disciplines. As this document evolves, more will be added to each section, and more sections will be added. However, I will not focus on teaching you the principal material itself. That will vary depending on the myriad decisions you must make along the way, and for each of those particulars there is a plethora of material online and in book stores for you to consume.

This essay is going to be written with the assumption that you are using Windows and are somewhat familiar with the computing metaphors it uses as well as some of the tools it provides. If you use a different operating system, it will be assumed that you know about Windows computing metaphors and how your operating system is different, and will be able to make sense of this document anyway.

>Formatting note: This document will use block quotes for both quotations as well as sidebars, such as this. Markdown, as far as I know, does not provide a good way to create sidebars, so for now this will have to do. If only there was some sort of general-purpose markup language and styling system that was highly mature with widely-recognized support...

### The Environment

>‟I believe OS/2 is destined to be the most important operating system, and possibly program, of all time.”  
— Bill Gates

Unless you are writing your own boot-sector and booting your computer into your program, you are writing your program within a computing context provided by your operating system (OS). This OS, such as Windows, Linux, or MacOS, is what your program is negotiating with. It is asking the OS to do things for you like write to the console, open files, draw graphics, print documents, make network connections, etc. Each OS has different ways of doing things, so as you learn to program, eventually you will be doing things that are specific to your OS. But in addition to that, the way you use the tools that you need to write programs, how you start and stop your programs, and how you pass information to these programs that tell it more specifically what you want to do, all will vary depending on your OS. This is going to have an effect on how you develop your software.

>The exception to this is with web development. While the developers of the different web browsers strive to provide a consistent standard for web developers, it is not perfect. Furthermore, clients have different screen dimensions and input methods that will effect how you design your product.

You will need to know how to use the command-line processors (shell) on your system. In Windows, this is _cmd_ and _PowerShell_, whereas on Linux it could be _bash_, _korn_, _zsh_, _fish_, and/or _csh_(to name just a tiny few of the myriad). You will need to understand how to navigate your file system and invoke programs and pass in parameters to those programs from the shell. Take some time to learn about your shell's quality-of-life features, including autocompletion and command history (try using the `<Tab>` and `<Up Arrow>` keys). They will make your life much easier. You will need to understand how programs are found when they are not in your _current working directory_ (i.e. the _search path_) and how to add directories to this list. You might even need to understand what environment variables are and how to add to them. One thing that I think is important enough to make special mention of is how to pass a single argument that has spaces in it. Do it by wrapping the argument in quotation marks (e.g. `myproggie -f "My Folder\That file.txt"`).

### The Toolchain
>‟The tools we use have a profound (and devious!) influence on our thinking habits, and, therefore, on our thinking abilities.”  
– E. Dijkstra

In the course of writing your programs, you will inevitably use at least a few tools. C programmers will use a text editor, the compiler, the assembler, the linker, and maybe a debugger. Web developers will use a text editor and a web browser. Python programmers will use a text editor and the Python interpreter. Each language requires some specific tools to build or interpret the programs, and you will want some generic ones as well. Depending on your project you may have to bring in other tools as well, such as specialty calculators, profilers, graphics programs, etc.

For more complex projects, sometimes a build automation tool is used. This is a scripting tool that creates configuration files and ensures that requirements are met just for the build process, and gets objects built in the right order. Complex projects would otherwise become unbearable to maintain. This is not for the beginner to worry about.

Another tool that is becoming standard practice is the use of some kind of version control software. This is software that allows you to track the progression of your software and roll it back to any previous version. It also aids in development on multi-file projects that have multiple contributors. It allows for a team of people to merge their work into a single project and offers utilities to detect and resolve some conflicts that arise from that strategy. It's not necessary to learn this up front, but don't put it off for too long. Soon, you will want to have your projects organized and available should you wish to open your source file to the public or create a portfolio for prospective employers.

You're going to want a programming text editor. This will take the place of Notepad and give you a much more feature-rich, content-aware text editor that will be helpful in writing source code files as well as other kinds of structured plain text files such as JSON, XML, and various configuration files. Here's a good selection of text editors to choose from:

* [Visual Studio Code](https://code.visualstudio.com/) (most popular)
* [Atom](https://atom.io/) (very pretty)
* [Brackets](https://brackets.io/) (unique web development feature)
* [Sublime Text](https://sublimetext.com/) (renowned, but not free)
* [Notepad++](https://notepad-plus-plus.org/) (very mature)
* [Kate](https://kate-editor.org/) (my choice)

Sometimes, instead of using several disparate programs, the programmer will use an _Integrated Development Environment_ (IDE) which combines the text editor, debugger, profiler, compiler, assembler, linker, and many other tools into one "easy-to-use" (not really) package. When properly configured, an IDE allows the programmer to write and test code with just the click of a single button. These IDEs support multiple languages, although some of them had origins as an IDE for projects of a specific language:

* [Visual Studio](https://visualstudio.microsoft.com/downloads/)
* [Eclipse](https://eclipse.org/) (Java origins)
* [Code::Blocks](https://codeblocks.org/) (C/C++ origins)
* [Komodo IDE](https://activestate.com/products/komodo-ide/) (Python origins)

Jetbrains offers a selection of language-specific IDEs, some free, others not. Here are the free ones:
* [IntelliJ IDEA](https://jetbrains.com/idea/) (Java)
* [PyCharm](https://www.jetbrains.com/pycharm/) (Python)

With the exception of Sublime Text, every program listed in this section is free. What a time to be alive!

In order to program in a language, you will need to have the build tools or interpreter for that language. For [ECMAScript](https://developer.mozilla.org/en-US/docs/Web/javascript/) you already have everything you need, which is a text editor and a web browser. Here are just a few languages you might be interested in learning about, as well as links to their project home pages:

* [Python](https://python.org/)
* [Java](https://oracle.com/java/technologies/downloads/)
* [Ruby](https://www.ruby-lang.org/)
* [Perl](https://perl.org/)
* [R](https://r-project.org/)
* [Rust](https://rust-lang.org/)
* [Go](https://golang.org/)
* [PHP](https://php.net/)

For web development, you'll need to learn the following three languages:
* [HTML](https://developer.mozilla.org/en-US/docs/Glossary/HTML)
* [CSS](https://developer.mozilla.org/en-US/docs/Glossary/CSS)
* [JavaScript](https://developer.mozilla.org/en-US/docs/Glossary/JavaScript)

For C/C++, consider using Visual Studio, Code::Blocks, or Eclipse. If you really just want a basic compiler/assembler/linker for Windows, you can get [MinGW-W64](https://www.mingw-w64.org/downloads/#mingw-builds) This will also get you a [Fortran](https://fortran-lang.org/) compiler.

### The Grammar and Syntax

>‟The only way to learn a new programming language is by writing programs in it.”  
— B. Kernighan & D. Ritchie

At some point, you will choose a language in which to write your programs. Just like natural languages, programming languages have a grammar and a syntax. Unlike natural languages, they must be adhered to strictly. Human beings are not accustomed to the level of precision necessary to write programs, so often we will get frustrated because we didn't place one semi-colon or parenthesis in the right place, causing our program to fail to build or behave incorrectly once built. Understand that this is a universal experience. With experience, this gets better, but it never goes away entirely. Experts still occasionally misplace a comma, or mismatch aquotation mark or parenthesis.

The choice of programming language for the purpose of learning to program shouldn't be given too much thought. In the course of your progression as a developer, you will learn at least a few, to varying degrees of competence. There are a few things you are going to need to learn in order to program in any _problem domain_.

>The exception to this is with web development. If you are going to study web development, you will need to learn the three specific languages mentioned in the previous chapter. You should start by learning how to write beautiful documents using HTML and CSS. These should all be treated as separate disciplines and the same rule of weaving your progress with these disciplines applies. That is to say, learn just a little bit of HTML, and then just a little bit of CSS, then start to learn JavaScript. Weave together the progress you make in these disciplines into a tightly-knit fabric.

You're going to have the urge to try to figure out what the best language is, or which is the most in-demand in the marketplace and base your decision on that. There isn't a best programming language and the market is fickle and capricious. Besides that, learning a language isn't that big of a commitment. Don't confuse learning a language with learning to program – they are two different things and you will not have to re-learn everything in order to pick up a new language.

### The Namespaces, Libraries, Modules and Assemblies

>‟There are only two hard things in Computer Science: cache invalidation and naming things.”  
— Phil Karlton

If you want to print to the console in C you will `#include <stdio.h>` and call `printf()`. In Python you will call the built-in function `print()` (or if you're still using Python 2 for some otherworldly reason, the keyword `print`). In C#, you will `using System;` and call `Console.Write()` or `Console.WriteLine()`. In Java, you will `import java.io.*;` and call `System.out.print()` or `System.out.println()`. In JavaScript, you will call `console.log()`.

There are many things like printing to the console that are common to many different languages, but they have different names and belong to different namespaces. Each language has a way to manipulate strings, open files, create and keep track of objects dynamically, do higher math, work with times and dates, etc. They usually work in similar and familiar ways, but for each language you learn you will need to become familiar with what your language calls things. You will need to learn how the functions and objects on which you will be relying are organized and how you can include them in your program.

### Programming Fundamentals

>‟The programmer, like the poet, works only slightly removed from pure thought-stuff. He builds castles in the air, from air, creating by exertion of the imagination. Few media of creation are so flexible, so easy to polish and rework, so readily capable of realizing grand conceptual structures. Yet the program construct, unlike the poet's words, is real in the sense that it moves and works, producing visible outputs separate from the construct itself. It prints results, draws pictures, produces sounds, moves arms. The magic of myth and legend has come true in our time. One types the correct incantation on a keyboard, and a display screen comes to life, showing things that never were nor could be. ... The computer resembles the magic of legend in this respect, too. If one character, one pause, of the incantation is not strictly in proper form, the magic doesn't work. Human beings are not accustomed to being perfect, and few areas of human activity demand it. Adjusting to the requirement for perfection is, I think, the most difficult part of learning to program.”  
— F. Brooks ("The Mythical Man Month")

Just like everything in the universe is made of protons, electrons, and neutrons, everything in a computer program is made of sequence, selection, and iteration. 

Computer programs are all made of the same stuff no matter what language or platform you are using. Certain things are true everywhere. For example, a loop that runs 100 times inside another loop that runs 100 times runs 10,000 times. Your program will spend most of its time in the inner-most loops. This is true in every language.

Some algorithms are faster than others. Sometimes, an algorithm is faster for smaller data sets than another algorithm that accomplishes the same thing which is faster for larger data sets.

There are different kinds of time in which an algoritm can run, and _big-O notation_ describes it. Look that up!

>‟The art of programming is the art of organizing complexity, of mastering multitude and avoiding its bastard chaos.”  
— E. Dijkstra (in "Notes on Structured Programming")

This is _information science_. There is so much to know on this topic that you can get a B.S. degree (or even a Ph.D) in it. These fundamentals are true everywhere and at all times. They are separate from the specific details of the language you are learning, and the namespaces and libraries that go with it. Once you have learned enough about your computing environment, tools, and language to be effective, you will find that this is the only thing left that you're still really learning, and you will be learning it forever. Languages and tools come and go, but _information science_ is forever.

### Reading Documentation

>‟The competent programmer is fully aware of the strictly limited size of his own skull; therefore he approaches the programming task in full humility, and among other things he avoids clever tricks like the plague.”  
— E. Dijkstra (in "The Humble Programmer", his 1972 Turing Award Lecture)

You will forget how to open a file in Python. You will also forget how to search for a substring in a string, or join a list of strings together. You will forget the conversion specifier for floating points when you want to see two leading zeroes and three places of precision on all the number printouts. You will forget how to declare a struct in C and you will definitely forget the arguments to `CreateWindowEx()`. Not only will you forget, you will forget sooner than you think.

That's why programming languages are meticulously and rigorously documented. These documents all look about the same, too. If you've seen one language's documentation, you've seen them all. When you are programming, you will always have the documentation to your language open in a browser and that browser will accumulate many tabs.

It is not your job as a programmer to remember how to do things. It's your job to know how to read the documentation (or search the internet for targeted solutions) and figure it out. The sheer volume of function and class names, modules, argument lists, language features, operators, and trivia about the language you are using is scant fathomable. As I write this, there are four tabs open to the _markdown_ documentation and this document itself as I go through the edit/test cycle to see it become what I want.

## Other Topics

Although the following topics weren't mentioned as the disciplines you need to learn in order to begin programming, they are nonetheless valuable, so they will be included here.

### Getting Help

>‟Another effective technique is to explain your code to someone else. This will often cause you to explain the bug to yourself. Sometimes it takes no more than a few sentences, followed by an embarrassed "Never mind, I see what's wrong. Sorry to bother you." This works remarkably well; you can even use non-programmers as listeners. One university computer center kept a teddy bear near the help desk. Students with mysterious bugs were required to explain them to the bear before they could speak to a human counselor.”  
— B. Kernighan & D. Pike (in "The Practice of Programming" pp. 123)

Eventually, you will come to a roadblock that you cannot overcome yourself. You will need to ask someone for personal help with a specific problem. This happens to all of us, and there are some people in the community who will help you. You can find them on the web in places like Stack Exchange, Stack Overflow, Quora, or any number of other forums. You can find help on chat media such as Internet Relay Chat (IRC) – which is still a thing – and newer ones like Discord, Matrix, and Telegram. You can look on the internet anywhere people gather to parley. Sometimes you won't get any traction in one venue but you will in another. Learn all the ways of getting help and use them as needed.

Please be kind and courteous. Helpers are not getting paid for it and most of them are stuck with their own programming problems. In fact, they went there to get help themselves and a bunch of newbies showed up asking questions they were able to answer so they just stuck around and answered the easy questions so that the wizards could answer theirs.

Describing your problem in a way that can be understood is a skill. Put as much effort into asking your question as you would expect them to put into answering it.

If you are asking for help in a real-time service like IRC or Discord, you may not get an answer in a few seconds, or even a few minutes. If the channel is slow, it might take hours for someone to notice your question and respond. Be patient. If the channel is busy and your question is several pages off the screen, you might ask again, but just know that people who are on IRC (and the like) usually have the client open in the background while they do other things.

## Finally

As you can see, there is a lot to learn right up front. It's a very steep climb in the beginning, but it's doable. Allow it to take time – don't rush it. Spend some time in each of these areas learning new things. Learn about your shell and OS environment, and how they work with your toolchain. Learn more about the grammar and syntax of your programming language, and take the time to explore standard included modules and libraries. Also take some time to explore the add-on modules that the community has made, and learn how to extend your programming environment with them. And last, but greatest, don't neglect the fundamentals. Listen to online lectures about programming paradigms and different kinds of algorithms. Learn about writing clear, readable code. Learn about structuring your programs in a way that makes them easier for you and others to maintain. You will find that as you start to get a grip on all of these disciplines, learning more becomes easier. New languages will fit into your knowledge like a puzzle piece that has somewhere to go.

>“You have to honor failure, because failure is just the negative space around success.”  
— R. Nelson (in Wired 06/2004)

When your program doesn't compile, you feel stupid. When it does compile but doesn't do what you want, you feel like a failure. This is what programming is; don't let this feeling stop you from pushing ahead. The moment your program compiles and does exactly what you want only exists as the final moment at the very end of the development process. It means your program is finished. If your program takes six months to develop, it's six months of blow after blow to your self-image. It feels like constant ongoing failure. _This is normal._ We are all squishy noodle-brains who think irrationally, take shortcuts, make mistakes, and forget things. We don't fully understand the problems we are trying to solve. We, in our inglorious failings, are trying to use cold, relentless, perfected machines to mechanize our casual, poorly-formulated thoughts. Our computers expose our inadequacy to ourselves, and it's humiliating, but the payoff is worth it. For so much as we are forced to see what sloppy thinkers we are most of the time, when a project is finished we get a glimpse of the genius we are sometimes capable of, and that genius gets mechanized and projected into the world with great force!

>“Then Dennis and Brian worked on a truly warped version of Pascal, called "A." When we found others were actually trying to create real programs with A, we quickly added additional cryptic features and evolved into B, BCPL, and finally C. We stopped when we got a clean compile on the following syntax:  
`for(;P("\n"),R=;P("|"))for(e=C;e=P("_"+(*u++/8)%2))P("|"+(*u/4)%2);`  
“To think that modern programmers would try to use a language that allowed such a statement was beyond our comprehension! We actually thought of selling this to the Soviets to set their computer science progress back 20 or more years”.  
— Simson Garfinkel & Steven Strassmann ("The Unix-Hater's Handbook")
