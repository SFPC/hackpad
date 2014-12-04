# Input/Output 04-22 Notes

Before this we all worked on our programming languages. 

---

Discussion about Processing versus openFrameworks. Processing is like having a learners permit as a teenager. openFrameworks is like being an adult with a full lisence. margin for error is greater, but you can go farther. Also, datatypes is weird in Java.

[Zach Lieberman](/ep/profile/AUZb6pnTdHj) is pro code on a page, not on a screen. Code is typography. Super important to remember this. The easiest code to understand is no code. The best way to learn is to not look at code, but rather to organize it. Think of it as a hypertext way of writing, not a linear way of writing. you don't have to think about what's in the link. you can drill down to look at what's there in the link, but you don't have to. There is the option of abstraction that is very powerful. 

He sees people get really tripped up with organizing the code. It's easy to get lost in code in terms of context so organization is really important.

Horror story time:

[Zach and Golan Levin] were working together to track people on stage and track their voices [messa di voce [](http://www.flong.com/projects/messa/)http://www.flong.com/projects/messa/]. some live performance thing. had a student come to meet them to help with the project. the student flew out, drank red bull non stop, wrote a totally unintelligible codebase. it seemed to work, but didn't actually work when they got to the theater. there was a function called 'process' that was 7 pages long. it was crazy, so much in there, poorly stuctured. it was a nightmare. Zach went to the press office and printed it out to be able to sort out what was going on. Zach could find the bugs when it was on paper. 

Moral: We get lost on the computer screen. We need new ways of thinking through our code. 

*   Now I understand why we're given all these recommendations of print books to read.

Muscle memory for typing code.

Writing on paper as a means of learning.

![](https://hackpad-attachments.s3.amazonaws.com/hackpad.com_h4bODX9BDUa_p.77541_1398182793204_20140422_120036.jpg)

We'll be defining the words that are circled. Those are the terms people didn't feel super comfortable with.

--

**Story**

*   What happens when you write code.
*   Your program begins as texts

--

![](https://hackpad-attachments.s3.amazonaws.com/hackpad.com_h4bODX9BDUa_p.77541_1398189241426_20140422_134839.jpg)

**<u>Variety of Datatypes </u>**

*   Datatypes is a way to define the limits.

        *   You are using 0 and 1 to represent something.

*   C and C++ you call these primitive datatypes

<u>Ints</u> - 32

<u>Long long</u> - 64 (Ginormous)

<u>Floating</u> - Can do about seven decimals places.

*   3.0000000
*   When using animation code typically you can use a float.
*   As you get further away from 0 the less values that this number can represent.

<u>Double</u> - more precise than a float use mostly by scientist where those differences matter.

<u>Boolean</u> - represent true and false.

<u>String</u> - letters

**Differences in Languages**

*   Stringly typed

        *   Java

                *   var x = 5
        *   x = "hello"

        *   C++

                *   float x = 100.05;
        *   Cant change the type because your asking the cpu to give you space in memory specifically for a float.
        *   You can't put a string in there.

*   Weakly typed

        *   You can play with languages in different ways
    *   A strings  + an int
    *   Weakly typed languages have all of these typed of existential questions.

**C and C++**

*   **Variables**

        *   This name a reserved for a place in memory.

                *   Placeholders for **memory.**
        *   Memory - the idea that we can store information. Which lets us do things overtime.
        *   Memory that you have used is called [the stack.](http://en.wikipedia.org/wiki/Stack_(abstract_data_type))
        *   C++ doesn't care where you are looking in memory.

                        *   An address position that you can look around in.
            *   Going from a student permit to your parents are not in the car.

                *   You can't initialize variables twice.

                        *   ![](https://hackpad-attachments.s3.amazonaws.com/hackpad.com_h4bODX9BDUa_p.77541_1398191012497_boy-driver-1-600x450.png)

        *   Stages of a variables life.

                *   Define the varibale
        *   put a value in
        *   get value out
        *   goodbye!

*   Words in code that you can't use to create variables (reserved).
*   Turns a color saying that these word is important.
*   If you compile in 32 bits you can only use that amount of memory.  (32 bits can address 4 billion positions in memory, ie 4 gb)
*   A limitation compared to 64 bits.
*   Drawing Memory
*   Old Mac Computers -- non protected memory

        *   Get a bomb
    *   Unhappy Face

                *   ![](https://hackpad-attachments.s3.amazonaws.com/hackpad.com_h4bODX9BDUa_p.77541_1398191709981_SadMac.gif)

        *   Looks very similar to analog feedback and CRT.

*   Sometimes there is protected space.
*   Memory Glitch that happened to me in THREE.js

*

[](http://www.youtube.com/watch?v=Cv2lJhCrM7I)http://www.youtube.com/watch?v=Cv2lJhCrM7I

**Objects**

*   The moment that you can start defining an object is the moment you can start creating your own code.