# Beginning Programming
## Preface
Programming computers is not a beginner-friendly endeavor. Part of the problem is that, unlike most other pursuits, there is no clear beginning. There are many places that are _the beginning_, as it were. In order to begin, you must become a novice in seven key areas all at once. They are:
* The environment
* The run-time system
* The toolchain
* The grammar and syntax
* The namespaces, libraries and/or modules
* Programming fundamentals
* Reading Documentation

This makes learning to code a daunting task to the uninitiated. Now that you know this, it should all be far less scary. The purpose of this essay is to give the reader a general understanding of the lay of the land, so he or she can direct his or her efforts sensibly without any undue frustration. If you have read this far, then you are already much more equipped to begin learning to program than you were before.

In the following chapters, I will describe to you _what_ these things are, as well as some other helpful topics as this document evolves. However, I will not focus on teaching you the material itself. That is your endeavor, which varies according to a whole slew of decisions that you must make. There is no shortage of tutorials, documents, and other explanatory works on these matters. It is only important that you know what these things are so that you know you must learn them, and why.

### The Environment

Computer programs are created to run on a certain microarchitecture. That is to say, when you make one, you make it for a certain type of computer. But unless you are writing your own boot-sector program, you are also writing your program for a certain operating system (OS). This operating system, such as Windows, Linux, or MacOS, is what you, the programmer, are negotiating with. You are asking the operating system to do things for you like open files, draw graphics, print documents, make network connections, etc. Each OS has different ways of doing things, so as you learn to program, eventually you will be doing things that are specific to a certain OS. The run-time environment is what you are using to make those requests, which I will cover a little later. Those who maintain runt-time environments endeavor to make as much as possible the same from OS to OS, but eventually, you will face OS particulars.

You will need to know how to use terminal console on your system. In Windows, this is _cmd_ or _PowerShell_, whereas on Linux it could be _bash_ or _csh_ or _zsh_ (but it's probably _bash_). You will need to understand how to navigate your file system and invoke programs and pass in parameters to those programs from the command-line interface. Take some time to learn about your console's quality-of-life features, including autocompletion and command history. Hint: it's the `<Tab>` and `<Up Arrow>` keys. They will make your life much easier. One more thing to know is that if you need to pass as a single argument, something that has spaces in it, it should be wrapped in quotes. The console will treat it as a single item and pass it into your program as such.

### The Run-time System

When you choose a language in which to write your programs, you are choosing the _run-time system_ (or, for short "_the run-time_") that goes with that language. This is a piece of software that plugs into your OS and povides the OS a way to execute the programs you write. You don't need to know much about it, other than each language has one (in one form or another), it is up to the maintainers of the language to maintain it. It needs to be present for programs written "against" it to run. That means if you want to create an installer and share your program with the world, you will also have to make sure the user also has the appropriate run-time system installed. If you have ever run a program only to be told, "This program requires MSVCRT90.DLL to run," or something similar, you have been on the receiving end of this problem. Usually, you just go and install the appropriate run-time system and you're good to go. This is a problem best tackled later.

### The Toolchain

In the course of writing your programs, you will inevitably use at least a few tools. C programmers will use a text editor, a compiler, an assembler, a linker, and maybe a debugger. Web developers will use a text editor and a web browser. Python programmers will use a text editor and the Python interpreter. Usually, the C programmer only thinks about the text editor and the compiler, as the rest of the build process is pretty well-automated. So the C programmer will write a text file, save it, invoke their compiler with it, which will result in an executable binary file being written to disk, and then run that binary program to see their program work. Python programmers will invoke the Python interpreter with their script and the Python interpreter will run it directly. Web developers will embed some JavaScript into an HTML document and load that file with their browser, and the browser will execute the JavaScript.

Sometimes, instead of using several disparate programs, the programmer will use an _Integrated Development Environment_ which combines the text editor, debugger, profiler, compiler, assembler, linker, and whatever other tools are needed into one "easy-to-use" package. When properly set up, the programmer can write some source code, save it, and from then on, just edit the code and press a _play_ button to have it saved, compiled, and run in one stroke. This makes the edit/test cycle much smoother.

For more complex projects, sometimes a build automation tool is used. This is a scripting language that creates configuration files, ensures requirements are met, and gets objects built in the right order so that complex projects don't become unbearable to maintain (as well as ensure the quality of the final build). This is not for the beginner to worry about.

### The Grammar and Syntax

>When we found others were actually trying to create real programs with A, we quickly added additional cryptic features and evolved into B, BCPL, and finally C. We stopped when we got a clean compile on the following syntax:

>`for(;P("n"),R=;P("|"))for(e=C;e=P("_"+(*u++/8)%2))P("|"+(*u/4)%2);`
>– Simson Garfinkel & Steven Strassmann ("The Unix-Hater's Handbook)

At some point, you will choose a language in which to write your programs. Just like natural languages, programming languages have a grammar and a syntax. Unlike natural languages, they must be adhered to strictly. Human beings are not accustomed to the level of precision necessary to write programs, so often we will get frustrated because we didn't place one semi-colon or parenthesis in the right place, causing our program to fail to build or behave incorrectly once built. Understand that this is a universal experience. It gets better, but it never goes away. Experts still leave off semi-colons, and mismatch quotations and parentheses, and have to edit their source a few more times to get it to compile.

### The Namespaces, Libraries and/or Modules

>There are only two hard things in Computer Science: cache invalidation and naming things.
>– Phil Karlton

If you want to print to the console in C you will include _stdio.h_ and call `printf()`. If you want to print to the console with Python you will call the built-in function `print()` (or if you're still using Python 2 for some otherworldly reason, the keyword `print`). If you are using C#, you will include _System_ it will be `Console.Write()` (or `Console.WriteLine()` depending on exactly what behavior you want). In Java, you will import _java.io.*_ and call `System.out.print()` or `System.out.println()`. In JavaScript, you will call `console.log()`.

There are many things like printing to the console that are common across many different languages, but they have different names and belong to different namespaces, and sometimes become available as a result of including certain headers or importing certain modules. They usually work pretty similarly, but you will need to become familiar with what your language calls things, and how the functions and objects on which you will be relying are organized and how you can include them in your program.

### Programming Fundamentals

>The programmer, like the poet, works only slightly removed from pure thought-stuff. He builds castles in the air, from air, creating by exertion of the imagination. Few media of creation are so flexible, so easy to polish and rework, so readily capable of realizing grand conceptual structures. Yet the program construct, unlike the poet's words, is real in the sense that it moves and works, producing visible outputs separate from the construct itself. It prints results, draws pictures, produces sounds, moves arms. The magic of myth and legend has come true in our time. One types the correct incantation on a keyboard, and a display screen comes to life, showing things that never were nor could be. ... The computer resembles the magic of legend in this respect, too. If one character, one pause, of the incantation is not strictly in proper form, the magic doesn't work. Human beings are not accustomed to being perfect, and few areas of human activity demand it. Adjusting to the requirement for perfection is, I think, the most difficult part of learning to program.
>– F. Brooks ("The Mythical Man Month", pages 7-8)

Everything in the universe is made of protons, electrons, and neutrons. Similarly, everything in a computer program is made of sequence, selection, and iteration. Someone will be along shortly to correct me on both of these statements. One statement leads to the next, programs that do more than one thing can branch to different parts of the program depending on a conditional test, and there are loops. Technically, a loop is really just a sequence combined with a selection between a jump back to the beginning or going through to the next statement (and a neutron is just a proton and electron combined into one particle).

Sequences of statements, if/then/else/switch statements (or _control flow_), and loops. Operators and operands, assignments, and evaluation. Computer programs are all made of the same stuff no matter what language or platform you are using. Certain things are true everywhere, such as a loop that runs 100 times inside another loop that runs 100 times runs 10,000 times. Keep it in mind. Your program will spend most of its time in the inner-most loops. Some algorithms are faster than others. Some are faster for smaller sets of data, and slower on larger ones, and some are faster on larger sets of data and slower on smaller ones (relative to other algorithms).

There are kinds of time and big-O notation. Look that up.

These are the kinds of things you will learn as you learn to program. There is much, much more. In fact, you can get a Bachelor's degree in it. But these fundamentals are true across the board. (A _functional_ programmer will be along shortly to correct me.) They are separate from the details of the language you are learning, and the namespaces and libraries that go with it. It is a separate discipline unto itself. In fact, this is the main discipline that you're learning – not some language or how to use Visual Studio. Languages and tools come and go, but nobody has invented a cure for _Computer Science_ yet.

### Reading Documentation

>The competent programmer is fully aware of the strictly limited size of his own skull; therefore he approaches the programming task in full humility, and among other things he avoids clever tricks like the plague.
>- E. Dijkstra (in "The Humble Programmer", his 1972 Turing Award Lecture)

You will forget how to open a file in Python. You wrote that part of the code six months ago. You remember how to open a socket and write some bytes to it, as well as all the nuance associated with blocking and non-blocking methods of doing so because that's what you were doing yesterday. You will also forget how to search for a substring in a string, or join a list of strings together. You will forget the conversion specifier for floating points when you want to see two leading zeroes and three places of precision. Not only will you forget, you will forget sooner than you think.

None of this is hard to do, but you will still forget. That's why programming languages are meticulously and rigorously documented. They all look about the same, too. When you are programming, the documentation is your significan other now. You and it are one. It is always open in your browser (with 12 tabs and on your second monitor). This is your life now.

## Other Topics

### Getting Help

Eventually, you will come to a roadblock that you cannot overcome yourself. You will need to pester someone with a question. This happens to all of us, and some of us are here for you. You can find us on the web in places like Stack Exchange or Stack Overflow, or any number of other forums. You can find us on Internet Relay Chat (IRC), which is still a thing. Learn how to use IRC. You can find us on Discord. You can find us on the internet anywhere people meet. Sometimes you won't get any traction in one place and you will in others. Learn all the ways of getting help and use them all as needed.

Please be kind and courteous. We are not getting paid for this and we're stuck with our own programming problems. In fact, we came here to get help ourselves and a bunch of newbies showed up asking questions we could answer so we just stuck around and answered the easy questions so the wizards could answer ours. You will also notice that there are people in there who know even less than, asking some very basic questions that even your newbie self can answer. Answer those questions so we can focus on yours. Then maybe think about sticking around.

Describing your problem in a way we can understand is a discipline. Put effort into learning this so that we don't have to play 20 questions with you. You will eventually get the hang of it.

If you are asking for help in a real-time service like IRC or Discord, you may not get an answer in a few seconds, or even a few minutes. If the channel is slow, it might be hours. Be patient. If the channel is busy and your question is several pages off the screen, you might ask again, but just know that people who are on IRC don't usually have their faces in the IRC client non-stop.

## Finally

>Programs must be written for people to read, and only incidentally for machines to execute.
>- H. Abelson and G. Sussman (in "The Structure and Interpretation of Computer Programs)

As you can see, there is a lot to learn right up front. It's a very steep climb in the beginning, but you can do it. Take it slowly; allow it to take time. You will find that as you start to get a grip on all of these disciplines, continuing to learn becomes easier. That is because you will not be re-learning everything every time you learn a new language or switch to a new text editor. The fundamentals will still be with you, and you will have a sense of the programming landscape.
