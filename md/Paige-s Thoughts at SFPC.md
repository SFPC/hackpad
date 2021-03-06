# Paige's Thoughts at SFPC

**GOALS CHECKLIST:**

*   blog consistently (goal is every day a week)
<ul class="task"><li>get more familiar with web development: ex) customize github blog</li>

*   create new portfolio site hosted on github
*   get comfortable with javascript
</ul class="task">

*   learn more processing - chapter a week with other students
*   get comfortable with d3

*   get comfortable with open frameworks
*   make lots of little things

*   make one big thing

*   teach something to someone

*   figure how I can keep making things after SFPC

**PROJECT IDEAS:**

**Language + code:**

There's been a huge focus in this class on education - I like this. There's a culturally imposed divide of skills that people can have: If you're good at reading/writing then you're probably not good at math; if you're good at math then you're probably not good at reading/writing. Most of the focus is centered on improving the way we teach people math/programming and making technology more accessible to them as its use becomes more prevalent in the world. I was lucky that math always clicked for me in school and I enjoyed it enough to study it at university. However, knowing that I liked math imposed an inherent lack of ability to write - I was terrified of english and lit classes. It was weird though, because I loved to read. I didn't really understand this disconnect fully until I came to SFPC. I made my circle visualization that I presented at the welcome party before coming or even knowing about SFPC based on pure curiosity. I didn't really have a clear intention of why I was doing it at the time. But after thinking more about it during my time here, I realized it was my attempt to make writing more math-y. This was the only way I could be comfortable with it. Thinking back, it also explains why I was so interested in my previous work experience at a startup whose products were built with natural language processing and linguistics concepts. IT'S ALL STARTING TO MAKE SENSE! So one project idea that I have is trying to make language more math-y, to help people like me and also other engineers for whom writing a paper was freaking huge deal in university. I guess this is my perspective on a 'new audience'.

I spoke with Sara Hendren about this and she suggested thinking about my 'new audience' as a younger group and to make pieces that can be a 'pretty' data viz at one level, but a teaching tool at another level: all focusing on this idea of making language more math-y.

Here's a few idea snippets I've had:

*   make circle viz interactive in d3, processing, or open frameworks

        *   have text read to you/move across screen while the circle viz is drawn out live, line by line

                *   have certain lines different colors based on sentiment or define drawing motion based on sentiment

                        *   maybe viz morphs through time based on cumulative sentiment?

                *   show live stats while animation is happening or show based on chapter, etc.
        *   is one letter more likely to correspond to works of a certain sentiment?

                        *   for a certain letter, are the words that use it more pos/neg or sub/obj?

*   more static circle viz where you can hover over chord and see words that contributed to that chord

        *   be able to choose a sequence of n letters and iterate around the circle
    *   have array of letter tuple frequencies - each word will have it's own letter tuple frequency array associated to it. Then for each word, check if the selected tuple has a nonzero entry in its frequency array-->but need a way to add more letters, so not to limit to tuples...??
    *   when displaying words, show how close each word is to next word in sequence (just look for first instance)
    *   search for a word and highlight sequence in image process for showing words when segments are moused over: we know what segment we have, segment i, so check count matrix for for diagonal i? to get paths?

*   have text read/move across screen where words disappear into a different type of viz based on some rules: sentiment, other natural language processing stats

        *   maybe they all join a different shape and shape can change size, color, when each word is added
    *   add sound when this happens?

*   interested in these viz with not only books/poems/other literature, but also personal data

        *   facebook statuses
    *   facebook, gchat messaging
    *   facebook posts
    *   twitter

*   getting even more meta:

        *   analyzing actual code text in the same way
    *   feed different code snippets into viz in the same way you'd feed a book
    *   need to account for more special characters

**Crochet + code:**

I really like crocheting...

**Crochet + language + code:**

Crochet poems: creating a pattern based on text. Maybe you can use a set of rules that are created based on sequences of characters in text to crochet a piece?

*   certain character sequences determine single/double/triple crochet
*   sentiment corresponds to color 
*   how can I use conductive yarn?