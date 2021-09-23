# Beginning Programming
>‟Programs must be written for people to read, and only incidentally for machines to execute.”  
— H. Abelson and G. Sussman (in "The Structure and Interpretation of Computer Programs")
## Preface
Programming computers is not a beginner-friendly endeavor. Part of the problem is that, unlike most other pursuits, there is no clear beginning. There are many places that are _the beginning_, as it were. In order to begin, you must become a novice in six key areas simultaneously. They are:
* The environment
* The toolchain
* The grammar and syntax
* The namespaces, libraries and/or modules
* Programming fundamentals
* Reading Documentation

This makes learning to code a daunting task to the uninitiated. The purpose of this essay is to give the reader a general understanding of the lay of the land, so he or she can direct his or her efforts sensibly without any undue frustration. If you have read this far, then you are already much better-equipped to begin learning to program than you were before.

In the following chapters, I will describe to you _what_ these things are, as well as some other helpful topics as this document evolves. However, I will not focus on teaching you the material itself. That is your burden, which varies depending on many things you must decide about how to proceed. There is no shortage of tutorials, documents, and other explanatory works on these matters. It is only important that you know what these things are so that you know you must learn them, and why.

### The Environment

>‟I believe OS/2 is destined to be the most important operating system, and possibly program, of all time.”  
— Bill Gates

Unless you are writing your own boot-sector and booting the computer into your program, you are writing your program for a certain operating system (OS). This OS, such as Windows, Linux, or MacOS, is what you are negotiating with. You are asking the OS to do things for you like open files, draw graphics, print documents, make network connections, etc. Each OS has different ways of doing things, so as you learn to program, eventually you will be doing things that are specific to a certain OS. Someone will be along shortly to correct me on this.

You will need to know how to use the command-line processors (shell) on your system. In Windows, this is _cmd_ and _PowerShell_, whereas on Linux it could be _bash_, _korn_, _zsh_, _fish_, and/or _csh_, to name just a tiny few of the myriad (but it's probably _bash_). You will need to understand how to navigate your file system and invoke programs and pass in parameters to those programs from the shell. Take some time to learn about your shell's quality-of-life features, including autocompletion and command history (it's the `<Tab>` and `<Up Arrow>` keys). They will make your life much easier. You will need to understand how programs are found (i.e. the _search path_) and how to add directories to this list. You might even need to understand what environment variables are and how to add to them. One more thing to know is that if you need to pass as a single argument something that has spaces in it, it should be wrapped in quotes (e.g. `myproggie -f "My Folder\That file.txt"`).

### The Toolchain
>‟The tools we use have a profound (and devious!) influence on our thinking habits, and, therefore, on our thinking abilities.”  
– E. Dijkstra

In the course of writing your programs, you will inevitably use at least a few tools. C programmers will use a text editor, a compiler, an assembler, a linker, and maybe a debugger, although the second usually automates the use of the rest thereafter. Web developers will use a text editor and a web browser. Python programmers will use a text editor and the Python interpreter.  So the C programmer will write a text file, save it, invoke their compiler and specify their source file. This will result in an executable binary file being written to disk, which he will then run to test his code. Python programmers will invoke the Python interpreter with their script and the Python interpreter will run it directly. Web developers will embed some JavaScript into an HTML document and load that file with their browser, and the browser will execute the JavaScript. A web developer will be along shortly to correct me on this.

Sometimes, instead of using several disparate programs, the programmer will use an _Integrated Development Environment_ which combines the text editor, debugger, profiler, compiler, assembler, linker, and whatever other tools are needed into one "easy-to-use" package. When properly configured, the programmer can write some source code, save it, and from then on, just edit the code and press a _play_ button to have it saved, compiled, and run in a single stroke. This makes the edit/test cycle much smoother.

For more complex projects, sometimes a build automation tool is used. This is a scripting language that creates configuration files, ensures requirements are met, and gets objects built in the right order so that complex projects don't become unbearable to maintain (as well as ensure the quality of the final build). This is not for the beginner to worry about.

You will need to find, download, and install the tools associated with the programming language you wish to use. Usually, it's pretty straightforward. If you want to learn [python.org](Python), go find and download the installer. It will install python, pythonw (for making GUI programs that don't have a console), IDLE (a text editor and live shell to the python interpreter), pip (a tool for adding addon packages to your installation), and perhaps a few other things. With [perl.org](Perl) it's the same way. Download whatever tools they use, read some "getting started" documents, usually on the same site, and just dive into it. If you want to learn C, C++, and/or C#, go and get an IDE called [visualstudio.microsoft.com/downloads/](Visual Studio) (Community edition). This is, in my opinion, Microsoft's crowning achievement – moreso than even Windows. It's a truly splendid suite of tools you can use to write programs in almost any language (though you may have to go download other things if you want to use Visual Studio for other languages like Python). Other languages you might be interested in might be, in no particular order, [ruby-lang.org](Ruby), [golang.org](Go), [php.net](PHP), [rust-lang.org](Rust), [oracle.com/java/technologies/downloads](Java) (get the Java SE Development Kit), and [r-project.org](R). These languages all serve different foci and have importantly different qualities. Some of them are interpreted, and some of them are compiled. Others compile to bytecode which then runs on a virtual machine which is implemented on all the major platforms. That basically means "mostly compiled" down to a stage where the virtual machine which interprets it has very little work left to do. That describes Java and C# in this list. This makes it easy to write code that runs on any platform without modifying the source code at all. Read about these languages and see how they compare and which kinds of problems they are designed to solve before choosing Python.

For [developer.mozilla.org/en-US/docs/Web/javascript](JavaScript) you already have everything you need, which is a text editor and a web browser. I would still recommend choosing a favorite text editor. On Windows, some of your choices include:
*[code.visualstudio.com](Visual Studio Code)
*[atom.io](Atom)
*[brackets.io](Brackets)
*[sublimetext.com](Sublime Text) (not free)
*[notepad-plus-plus.org](Notepad++)
*[kate-editor.org](Kate)

Some full-scale IDEs include:
*[visualstudio.microsoft.com/downloads/](Visual Studio)
*[eclipse.org](Eclipse)
*[codeblocks.org](Code::Blocks)
*[jetbrains.com/idea](IntelliJ IDEA)
*[activestate.com/products/komodo-ide](Komodo IDE)

### The Grammar and Syntax

>‟The only way to learn a new programming language is by writing programs in it.”  
— B. Kernighan & D. Ritchie


At some point, you will choose a language in which to write your programs. Just like natural languages, programming languages have a grammar and a syntax. Unlike natural languages, they must be adhered to strictly. Human beings are not accustomed to the level of precision necessary to write programs, so often we will get frustrated because we didn't place one semi-colon or parenthesis in the right place, causing our program to fail to build or behave incorrectly once built. Understand that this is a universal experience. It gets better, but it never goes away. Experts still leave off semi-colons, and mismatch quotations and parentheses, and have to edit their source a few more times to get it to compile.

### The Namespaces, Libraries, Modules and Assemblies

>‟There are only two hard things in Computer Science: cache invalidation and naming things.”  
— Phil Karlton

If you want to print to the console in C you will `#include <stdio.h>` and call `printf()`. If you want to print to the console with Python you will call the built-in function `print()` (or if you're still using Python 2 for some otherworldly reason, the keyword `print`). If you are using C#, you will `using System;` and call `Console.Write()` or `Console.WriteLine()` depending on exactly what behavior you want. In Java, you will `import java.io.*;` and call `System.out.print()` or `System.out.println()`. In JavaScript, you will call `console.log()`.

There are many things like printing to the console that are common to many different languages, but they have different names and belong to different namespaces, and sometimes become available as a result of _include_ -ing or _import_ -ing or _using_ -ing certain headers or modules or assemblies. Each language has a way to open files, manipulate strings, do higher math, etc. They usually work in similar and familiar ways, but for each language you learn you will need to become familiar with what your it calls things. You will need to learn how the functions and objects on which you will be relying are organized and how you can include them in your program.

### Programming Fundamentals

>‟The programmer, like the poet, works only slightly removed from pure thought-stuff. He builds castles in the air, from air, creating by exertion of the imagination. Few media of creation are so flexible, so easy to polish and rework, so readily capable of realizing grand conceptual structures. Yet the program construct, unlike the poet's words, is real in the sense that it moves and works, producing visible outputs separate from the construct itself. It prints results, draws pictures, produces sounds, moves arms. The magic of myth and legend has come true in our time. One types the correct incantation on a keyboard, and a display screen comes to life, showing things that never were nor could be. ... The computer resembles the magic of legend in this respect, too. If one character, one pause, of the incantation is not strictly in proper form, the magic doesn't work. Human beings are not accustomed to being perfect, and few areas of human activity demand it. Adjusting to the requirement for perfection is, I think, the most difficult part of learning to program.”  
— F. Brooks ("The Mythical Man Month")

Everything in the universe is made of protons, electrons, and neutrons. Similarly, everything in a computer program is made of sequence, selection, and iteration. Someone will be along shortly to correct me on both of these statements. Statements are executed in order, one after another, but comparisons can be made and programs can jump around to different places depending on the result of these comparisons. Technically, a loop is really just a sequence combined with a selection between a jump back to the beginning or going through to the next statement after the loop. Fitting, then, that a neutron is just a proton and electron combined into one particle.

Computer programs are all made of the same stuff no matter what language or platform you are using. Certain things are true everywhere. For example, a loop that runs 100 times inside another loop that runs 100 times runs 10,000 times. Your program will spend most of its time in the inner-most loops. This is true in every language.

Some algorithms are faster than others. In some sets of algorithms which do the same thing, some are better for smaller data sets and others for larger data sets. Some algorithms can use more memory to get a job done more quickly, and others can save memory by taking more steps to get the job done. This, too, is true in every language.

There are different kinds of time an algoritm can run in and _big-O notation_ describes it. Look that up!

>‟The art of programming is the art of organizing complexity, of mastering multitude and avoiding its bastard chaos.”  
— E. Dijkstra (in "Notes on Structured Programming")

These are the kinds of things you will learn as you learn to program. There is much, much more. In fact, you can get a bachelor's degree in it. But these fundamentals are true everywhere and at all times. (A _functional_ programmer will be along shortly to correct me.) They are separate from the details of the language you are learning, and the namespaces and libraries that go with it. It is a separate discipline unto itself. In fact, this is principally what you're learning. Languages and tools come and go, but _information science_ is forever.

### Reading Documentation

>‟The competent programmer is fully aware of the strictly limited size of his own skull; therefore he approaches the programming task in full humility, and among other things he avoids clever tricks like the plague.”  
— E. Dijkstra (in "The Humble Programmer", his 1972 Turing Award Lecture)

You will forget how to open a file in Python. You will also forget how to search for a substring in a string, or join a list of strings together. You will forget the conversion specifier for floating points when you want to see two leading zeroes and three places of precision. You will forget how to declare structs in C and you will definitely forget the arguments to `CreateWindowEx()`. Not only will you forget, you will forget sooner than you think.

None of these things are hard to do, but you will forget how to do them anyway. That's why programming languages are meticulously and rigorously documented. These documents all look about the same, too. When you are programming, you will always have the documentation to your language open in a browser and that browser will accumulate many tabs.

It is not your job as a programmer to remember how to do things. It's your job to know how to read the documentation and figure it out. The sheer volume of function and class names, modules, argument lists, language features, operators, and trivia about the language you are using is scant fathomable. As I write this, there are four tabs open to the _markdown_ documentation and this document itself as I go through the edit/test cycle to see it become what I want.

## Other Topics

Although the following topics weren't mentioned as the disciplines you need to learn in order to begin programming, they are nonetheless valuable, so they will be included here.

### Getting Help

>‟Another effective technique is to explain your code to someone else. This will often cause you to explain the bug to yourself. Sometimes it takes no more than a few sentences, followed by an embarrassed "Never mind, I see what's wrong. Sorry to bother you." This works remarkably well; you can even use non-programmers as listeners. One university computer center kept a teddy bear near the help desk. Students with mysterious bugs were required to explain them to the bear before they could speak to a human counselor.”  
— B. Kernighan & D. Pike (in "The Practice of Programming" pp. 123)

Eventually, you will come to a roadblock that you cannot overcome yourself. You will need to ask someone for personal help with a specific problem. This happens to all of us, and some of us are here for you. You can find us on the web in places like Stack Exchange, Stack Overflow, Quora, or any number of other forums. You can find us on chat media such as Internet Relay Chat (IRC) – which is still a thing – and newer ones like Discord, Matrix, and Telegram. You can find us on the internet anywhere people gather to parley. Sometimes you won't get any traction in one venue but you will in another. Learn all the ways of getting help and use them as needed.

Please be kind and courteous. We are not getting paid for this and we're stuck with our own programming problems. In fact, we came here to get help ourselves and a bunch of newbies showed up asking questions we could answer so we just stuck around and answered the easy questions so the wizards could answer ours. You might think you don't know anything, but you will notice that there are people in there who know even less than you, asking some very basic questions that you can answer. Answer those questions so we can focus on yours.

Describing your problem in a way we can understand is a skill. Put as much effort into asking your question as you would expect us to put into answering it.

If you are asking for help in a real-time service like IRC or Discord, you may not get an answer in a few seconds, or even a few minutes. If the channel is slow, it might take hours for someone to notice your question and respond. Be patient. If the channel is busy and your question is several pages off the screen, you might ask again, but just know that people who are on IRC usually have the client open in the background while they do other things.

## Finally

As you can see, there is a lot to learn right up front. It's a very steep climb in the beginning, but it's doable. Allow it to take time – don't rush it. You will find that as you start to get a grip on all of these disciplines, learning more becomes easier. Learning a new language won't involve learning fundamentals again. Using a new IDE or text editor doesn't mean starting from scratch. They all work about the same way.

>“You have to honor failure, because failure is just the negative space around success.”  
— R. Nelson (in Wired 06/2004)

When your program doesn't compile, you feel stupid. When it does compile but doesn't do what you want, you feel like a failure. This is what programming is; don't let this feeling bring you down. The moment your program compiles and does exactly what you want only exists as the final moment at the very end of the process. If your program takes six months to develop, it's six months of blow after blow to your ego and self-image. It hurts and it can be infuriating. _Do not let this feeling distract you from your goal!_ We are all in the same boat. We are all squishy noodle-brains who think irrationally, take shortcuts, make mistakes, and forget things. We don't fully understand the problems we are trying to solve. We, in our inglorious failings are trying to use cold, relentless machines to mechanize our poorly-formulated thoughts. Our computers expose our inadequacy to ourselves, and it's humiliating, but the payoff is worth it. Much as we see what sloppy thinkers we are most of the time, when a project is finished we get a glimpse of the genius we are sometimes capable of.

>“Then Dennis and Brian worked on a truly warped version of Pascal, called "A." When we found others were actually trying to create real programs with A, we quickly added additional cryptic features and evolved into B, BCPL, and finally C. We stopped when we got a clean compile on the following syntax:  
`for(;P("\n"),R=;P("|"))for(e=C;e=P("_"+(*u++/8)%2))P("|"+(*u/4)%2);`  
“To think that modern programmers would try to use a language that allowed such a statement was beyond our comprehension! We actually thought of selling this to the Soviets to set their computer science progress back 20 or more years”.  
— Simson Garfinkel & Steven Strassmann ("The Unix-Hater's Handbook")
