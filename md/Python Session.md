# Python Session

very **friendly** language for non-programmer

community is great

**scripting language**

code you write is only interpreted when it's necessary 

for writing small utilities

(for Zach) tends to be project to use for small things

**interpreted language**

simultaneous translation > reading line by line and turn that into instruction, not compile or think about the whole thing before start doing something. 

like live translation, will have a snag as soon as it hits an error

command line interface

C - variable tied to datatype

Python - **loose type** >> List of variable with different types

*   **loose variable types**

**High level**

doing a lot of processing is not so great

big games, image processing, photoshop

not something you'll write in python

Python have many **versions**

v3 came out a few years ago 

v2 still supported and Zach still use 2

v3 won't run on v2 compiler

mac shipped with python

you can use brew to install multiple version of **python**

and switch between versions

**Package Manager**

equivalent of npm in node

*   **pip**
*   **easy_install**

(BeautifulSoup)

HTML parsing library

**inspecting python**

Has something called [REPL](http://en.wikipedia.org/wiki/Read%E2%80%93eval%E2%80%93print_loop) – allows you to inspect what the code is doing. 

run 

*   $ python

in command line

you'll get 

*   >>> 

curser where you can test your code

*   add notes about using exit to debug

for example 

*   >>> print 'Hello World'
*   Hello world

you can use repl to test the language out, for example 

*   >>> x = "hello"
*   >>> y = "ll"
*   >>> x in y 
*   False
*   >>> y in x
*   True
*

ctrl + C to quit back to bash  (or better, type quit() )

**environment**

Zach use SublimeText for editor for python

command line tools works too, like vi, pico, emac

*   these stuffs is not very friendly though, pico is the most friendly

**Q: What is Regular expression? Regular expression python?**

is a grammar, for example, if you want to find an IP address in text 

1 2 3 dot

**save to a file**

anything that print out the the console can be printed in the file through piping

for example

*   python hello.py > oscar.txt

file I/O 

[](https://docs.python.org/2/tutorial/inputoutput.html)https://docs.python.org/2/tutorial/inputoutput.html

**Variable can be anything**

counter = 100

miles = 1000.0

name = 'John'

**Key value pairs**

(in pseudo code)

capitals["NY"] = "Albany"

capitals["IL"] = "Springfield"

List [ ]  <- just values

Dictionary {} <- has key vlaue pairings

*   tinydict = {'name': 'john','code':6734, 'dept': 'sales'}
*   print tinydict          # Prints complete dictionary
*   print tinydict.keys()   # Prints all the keys
*   print tinydict.values() # Prints all the values
*   print tinydict['name']

**Dictionary**

[Dictionary is a mapping from one thing to another](http://pythonarticles.com/python_dictionaries.html) . 

There is no order, unsorted. Can access things in the dictionary by a word (or the key), not a position number.  (In c++ we use "map" part of the STL)

**Big data sets**

Once you have something in [tab separated values](https://en.wikipedia.org/wiki/Tab-separated_values) , python can work with it. might need some data cleanup. There are tools, not necessarily Python code, the help clean up data. Results may vary.

CSV - library for working with tab separated value files. 

each row is a dictionary. not uncommon to have a list with dictionaries, or a dictionary with lists. 

**Resources** (python libraries to include in web scraping)

[beautifulsoup](http://www.crummy.com/software/BeautifulSoup/) - library for prasing xml and html data

[urllib](https://docs.python.org/2/library/urllib.html)  - loads a webpage

[re](https://docs.python.org/2/library/re.html)  - regular expressions operations

[opml](http://dev.opml.org/)  - "an XML-based format that allows exchange of outline-structured  information between applications running on different operating systems  and environments."

sleep - [](https://docs.python.org/2/library/time.html#time.sleep)https://docs.python.org/2/library/time.html#time.sleep

if you're scraping a site, you might need to do some rate limiting, dictate the speed at which class are made. 

there are also techniques for distributing request from different ip addresses

**Example - Bible Alphabetical:**

**   tr ' ' '\n' < a.txt >> b.txt
*   sort b.txt >> c.txt
*   tr '\n' ' ' < c.txt >> d.txt
*

(sort b.txt into a new file c.txt)

(change newlines to space in c.txt into a new file d.txt)

I think this doesn't deal with spaces and weird stuff (like words with punctuation)

but it's a start

--

use uniq to sort works by frequency - [](https://en.wikipedia.org/wiki/Uniq)[https://en.wikipedia.org/wiki/Uniq](https://en.wikipedia.org/wiki/Uniq)