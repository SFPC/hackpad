# Radical Computer Science

## Day One - program a dance

*   Radical computer science blog - [](http://radicalcomputerscience.tumblr.com/)http://radicalcomputerscience.tumblr.com/
*   Thinking about language design as a creative practice. 
*   code allows us to execute post human thoughts
*   ways of thinking that go beyond thinking as a human
*   code is a thought amplification device
*   this is structured by languages which are all human made, negotiated, a series of decisions.

*

[](http://dancingplagueof1518.tumblr.com/post/16848676522)http://dancingplagueof1518.tumblr.com/post/16848676522

*   think about what you think the person who wrote the language thought was important when they designed the language?
*   this is context dependent. C is from the 1960s, very different context to how we use it now.
*   No strings in C, difficult dealing with text. 
*   Question: if you have code and say it does something, how do you prove that it does that?

        *   eg. code managing a pace maker this is important
    *   code for video games, not such a big deal, malfunctions are opportunities. Often right and wrong is arbitrary.
    *   Next week: turing model computation

*   Code is like archeology. You are building on code that someone wrote (ususally in the mid 80s).
*   When you build a motorcycle, all parts are new rebuilt etc etc. We don't use parts from the 60s. 
*   We don't have the luxury with software dev.
*   Build on UNIX - you have an internet stack, audio stack, all this work built already. A PROFOUND amount of work. Build from scratch you have nothing.
*   Commodore 64 would boot into a basic prompt. Boot up interaction is a command line prompt. First interaction is that you have to write a command.
*   GateKeeper MaxOS (new feature in macOS) Won't let you run code unless it is from the app store. The error message is 'this app is corrupt and you should throw it away'. Now the basic way you talk to computers is by consumption (buying code), rather than creation as in (commodor 64). A BIG SHIFT! 

**Homework**

*   Pick an image from great art bot. And then generate a programming language (textural) that could generate this. Pick one image and go on a journey on how you might make it. Set of descriptions is enough. [](https://twitter.com/greatartbot)https://twitter.com/greatartbot
*   Review content on: [](http://radicalcomputerscience.tumblr.com/)[http://radicalcomputerscience.tumblr.com/](http://radicalcomputerscience.tumblr.com/) (contacts are here too) 

## Oct 20 - PuzzleScript

**Last week's assignment:**

*   Because we didn’t get a chance to work with <u>[plt.js](https://github.com/nasser/pltjs)</u> together, I decided not to assign any grammar homework this week. Focus on PuzzleScript, <u>[download](https://github.com/nasser/pltjs/archive/master.zip)</u> plt.js if you want to start playing with it, but we will spend next class getting started together.

**Challenges**

*   Make a game
*   Make something that is not a game
*   PuzzleScript site - [](http://www.puzzlescript.net/)http://www.puzzlescript.net/
*   Documentation - [](http://www.puzzlescript.net/Documentation/rules101.html)http://www.puzzlescript.net/Documentation/rules101.html

**This week's review**

*   Andrew's game - Fuck & Fu*k

[Ramsey Nasser](/ep/profile/yCuF2I2SWeJ) references 

*   [Life in Life](https://www.youtube.com/watch?v=xP5-iIeKXE8), Game of life is turing complete and can actually create the game of life in itself. 
*   Also [Langtons Ant](http://en.wikipedia.org/wiki/Langton's_ant) - it looks random until 10k iterations in then it always starts building a highway but with the initial rules there is no way to derive that behavior

Puzzlescript was made by a game designer and he wanted to create a language, not a tool

*   [cfxr](http://thirdcog.eu/apps/cfxr) is the sound engine

Because this is a focused language it forces you to work within a framework - people found this easier to work with and not feel overwhelmed. 

The language used by puzzlescript is a re-write engine. Its powerful but not used frequently. Another language that is similar is '[mathmatica](http://www.wolfram.com/mathematica/)'. 

In short it says - _whenever you see this one thing, do this other thing_. it is slow because it runs through all the permutations until it is done.

*   wolframtap - tweet a program - [](http://www.wolfram.com/language/tweet-a-program/)http://www.wolfram.com/language/tweet-a-program/
*   wolfram alpha - [](http://www.wolframalpha.com/)http://www.wolframalpha.com/

**Going Forward**

*   meet once a week
*   think about a final project ideally turing complete
*   will have code book club

**Review PLT.JS**

Download this: [](https://github.com/nasser/pltjs)https://github.com/nasser/pltjs then open the example.html in a text editor

1.  fun libraries he's referencing at the top of 'example.html' JQuery, PegJS (Parsing Expression Grammer) & SugarJS
2.  JS area, you can put shit in here. May be helpful to know a bit of JS or find a friend who can help you.
3.  Name your language in the 'title'
4.  peg syntax for reference is commented out
5.  write your syntax in the 'grammer' area
6.  examples that get rendered out on the page

To get started 

1.  probably a good idea to have a function in mind for your language like 'mess around with audio' or 'do some stuff with text and colors'. can pull in JS libraries to help with that

        1.  ex: quill, processing wrapped in clojure

2.  copy empty and then rename and start a new one

        1.  if you uncomment plt.refresh=true it will autorefresh

![](https://hackpad-attachments.s3.amazonaws.com/hackpad.com_e9tuvMkvwR9_p.252113_1413828684648_undefined)

1.  Reverse the text & change size

*   <code>Reverse foo</code>
*   <!-- arity --> (ability to do more than 1 type of action (ex: either numbers or language)
*   <code>size foo</code>
*   <code>size larger foo</code>
*   <span style="font-size:large">foo</span>

Diff bet. Operators and Actions are Actions are prefix & Operators are infix ex: rect(10, 20, 40, 50); //prefix & (6 * 7) //infix

*   <H3>Operators</H3>
*   <!-- infix -->
*   <code>red = blue</code>
*   <code>red + blue</code>
*   <code>red - blue</code>
*   ![](https://hackpad-attachments.s3.amazonaws.com/hackpad.com_e9tuvMkvwR9_p.252113_1413830017091_undefined)

Tips on text editing in Sublime Text

[](http://code.tutsplus.com/tutorials/sublime-text-2-tips-and-tricks-updated--net-21519)http://code.tutsplus.com/tutorials/sublime-text-2-tips-and-tricks-updated--net-21519

Now... Creating Grammar

All this code is here: [](https://gist.github.com/nasser/8e959377672c5c344fef)https://gist.github.com/nasser/8e959377672c5c344fef

*   --- when we defined tokens in the beginning ---
*   <grammar>
*   start = token //any character that's defined below
*   token = t:[a-zA-Z]+ { return { token: t.join("") } } //"-" will display any values between a to z on the ascii chart. "+" match the range of values one or more times. 'color' will assign the color to the text that will printed out, assigning the meaning. 't.join' will combine the separate letters into one string. 
*   //can also use [^ ] to parse token "^" means everything but the values that precede it so in this case it is " " space
*   </grammar>
*   --- when we defined actions after defining the tokens above---
*   <grammar>
*   start = action
*   action = n:token space a:token* space t:token 
*       { return {name:n.token, attributes:a, target:t.token } }
*   token = t:[a-zA-Z]+ { return { token: t.join("") } }
*   SPACE  = ' '+ mandatory
*   space  = ' '* optional
*   </grammar>

**Next week's homework**

*   will give incomplete grammar to label and parse

## Oct 27th

Review PostScript

*   video tutorial [](http://www.youtube.com/watch?v=S_NXz7I5dQc)<u>[http://www.youtube.com/watch?v=S_NXz7I5dQc](http://www.youtube.com/watch?v=S_NXz7I5dQc)</u>
*   making images [](http://paulbourke.net/dataformats/postscript/)http://paulbourke.net/dataformats/postscript/
*   dejong examples - [](http://www.kerrymitchellart.com/tutorials/generalized-de-jong/sample3.html)http://www.kerrymitchellart.com/tutorials/generalized-de-jong/sample3.html
*   OMG this guy has a zillion postscript tutorials - [](http://www.tinaja.com/post01.shtml)http://www.tinaja.com/post01.shtml
*   what was the experience? the language may be great but if there is no documentation/tutorials/community around it then the experience is bad

**Stack Languages**

*   more transparent about what they are doing so the history of calculations can be seen
*   the way the interface works is the language is on the left and the 'repl' (read, evaluate, print, loop) is on right. this allows you to make changes (on left) and test changes (on right)

        *   'control + comma + b' in sublime will send your changes on the left to the repl

*   {...} is a way to define functions and variables

*   (rejoyce { doub [dub +]} 7 doub)
*   (rejoyce {const 14} 1 2 const 3 4 const) // as a variable
*   (rejoyce {const 14} 1 2 const {const 28} 3 4 const) // renaming variable

*   Are there loops? yes in factor (looks like):

*   [10 20 <] [300] [400] if

Conditionals/loops etc just like functions 

You can design your own conditionals:

*   (0.5(...) 0.25(...) 0.25(...) chance)
*   //break up by probibility

**Identities and Values**

*   fundamental difference bet. a value and a place to store the value. 

        *   In JavaScript when you assign a variable then reassign the variable with a new value, the old value is still in the program - it's just not assigned to that variable
    *   e.g. var name = "sfpc" then var name = "not sfpc"

*   'name' is the identity where 'sfpc' or 'not sfpc' are the variables
*   '=' means 'should point to' not 'equals
*   When you assign a variable to a new value, the old one is still there in memory until removed by the garbage collector (important feature of modern programming)

*   var foo = ({ first: "sf", last: "pc"})
*   Object {first: "sf",  last:"pc"}
*   foo.last = "poetic computation" //renames the value and then the initial value is lost

*   URL is an example of a place/identity, not a value
*   Immutable data -> cannot be changed

        *   var foo = ({space: "taco", ship: "burrito})
    *   just points to 1 object in the set of all possible objects, like 13 is one number in the set of all numbers. If you change 'foo' it would just point somewhere else, the object would still exist
    *   in a persistent data structure, whenever a value is changed it creates a new version of it leaving the old one intact and still acessible
    *   more here: [](http://en.wikipedia.org/wiki/Persistent_data_structure)[http://en.wikipedia.org/wiki/Persistent_data_structure](http://en.wikipedia.org/wiki/Persistent_data_structure)

**Review Homework & Next Steps**

*   why the hell do the strings have '\' - it's because the escape character \ is not getting parsed out. e.g.:

*   word      = '"' w:[^"]+ '"' {return w.join("") }

*   'eval' you can give any code and it will run it as JS (in browser)
*   in order to do multiple things you HAVE to give things name and call those in some order e.g. start = number/word/boolean...

lists:

*   = '[' l:number* ']' {return l}

*   supporting lists in a list

*   = '[' ' '* l:(string / number / list)* ']' ' '* {return l}

numbers

*   numbers  = digits:[0-9.-]+ { return parseFloat(digits.join('') ) } 
*

this is a cute thing about clojure that has a lot of explanations: [](http://www.braveclojure.com/)[http://www.braveclojure.com/](http://www.braveclojure.com/)