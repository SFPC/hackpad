# Learning to learn

editing

_[ Note this is going to have a course description and a bunch of notes.  just testing how hackpad works and adding some notes from my class here...  ]_

_There are only 10 different kinds of people in the world:_

_those who know binary and those who don't._

                                            -  Anonymous 

_Our computer successfully creates the illusion that it_

_contains photographs, letters, songs, and movies. All it_

_really contains is bits, lots of them, patterned in ways_

_you can't see.  Your computer was designed to store just_

_bits - all the files and folders and different kinds of_

_data are illusions created by computer programmers._

**Asking Questions**

We spent time in class coming up with a list of questions.  

*   what are simple ways of teaching people how to code?
*   how do analog computers work?
*   how do software patents work?  
*   what alternative models of computation are there?  quantam computing etc. 
*   how does cryptography, esp as it relates to random number generation and breaking crypto work?
*   what does a monad mean?
*   what is a lambda expression
*   how do you translate a mathmatical paper into code?
*   what are people's first programming language and how does it color their opinions of what's possible?
*   todays computers are electrical, what are the alternatives?
*   what is the origin of different toolkits like processing and arduino?
*   what tools do we need now?
*   who is the first programmer?
*   how does opencl / distributed programming work?
*   what is node.js, why would I use it?
*   what is the hardest, most esoteric, computer language?
*   what are templates in c++, and how do we use them effectively?  why would you use them?

_Homework 1:  Write code in a language you have no experience with. _

**Binary Numbers**

_Homework 2:  Build a tool to show someone the concept of binary numbers_

**Variables**

*

*   name

        *   (sometimes start with something, perl = $)
    *   python no puctuation
    *   typically can't start with digit
    *   single letter names for small things, like "i" for iterator

*   data types

        *   primary types

                *   integer
        *   byte (char) 0,1,255
        *   floating point
        *   strings

*   value
*   arrays

_Homework 3:  Create sketches with interesting variable names?  Can you tell a story, or a joke, or a poem through code?   See Ishac's code poem book for inspiration.  What is the scariest variable name you can make?  What is the most important variable personally you can make?  etc.  think about the Name, Type and Value of the variable. _

*

**Control Structures**

**Functions **

**Objects**

_Object-oriented programming is an exceptionally bad idea which could only have originated in California. - dijkstra_

_A programming language serves two related purposes: it provides a vehicle for the programmer to specify actions to be executed and a set of concepts for the programmer to use when thinking about what can be done. The first aspect ideally requires a language that is "close to the machine", so that all important aspects of a machine are handled simply and efficiently in a way that is reasonably obvious to the programmer. The C language was primarily designed with this in mind. The second aspect ideally requires a language that is "close to the problem to be solved" so that the concepts of a solution can be expressed directly and concisely. The facilities added to C to create C++ were primarily designed with this in mind.  -- Bjarne Stroustrup_

*   data structures

        *   data structure is a group of data elements grouped together under one name
    *   data elements, _members_, can have different types and different lengths
    *   dot (.) between object name and member name

                *   apple.weight
        *   apple.price
        *   banana.weight
        *   banana.price
        *   melon.weight
        *   melon.price

        *   feels a bit like relational databases (spreadsheet)

                *   [](http://computer.howstuffworks.com/question599.htm)[http://computer.howstuffworks.com/question599.htm](http://computer.howstuffworks.com/question599.htm)

        *   typedef
    *   all "public"
    *   [](http://www.tldp.org/LDP/tlk/ds/ds.html)[http://www.tldp.org/LDP/tlk/ds/ds.html](http://www.tldp.org/LDP/tlk/ds/ds.html)

lots of pro / cons: 

*   [](http://c2.com/cgi/wiki?ArgumentsAgainstOop)http://c2.com/cgi/wiki?ArgumentsAgainstOop
*   [](http://c2.com/cgi/wiki?BenefitsOfOo)http://c2.com/cgi/wiki?BenefitsOfOo
*   [](http://harmful.cat-v.org/software/OO_programming/)http://harmful.cat-v.org/software/OO_programming/

useful: 

*   [](http://processing.org/tutorials/objects/)http://processing.org/tutorials/objects/

_Homework 4: Think about metaphors and specifically, how you can describe programming concepts for non programmers.  How can whimsy and play be effective teaching tools?  What alternative ways of viewing these concpets can help explain them?  Build a tool to help explain one or more of the concepts we've been reviewing: variables, control structures, and objects._