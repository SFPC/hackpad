# Parsed Poetry Programming Language

Search Engine Dependent Parsing Programming Language

*   apologies for the weird name don't know how else to describe this project at the time!
*    this is a hackpad for breaking down the steps it would take to make the programming language that [Jason Levine](/ep/profile/m5rLOYYylrl) and [Claire Lin](/ep/profile/sOovaDOwuJq) proposed in [Amit Pitaru](/ep/profile/tkesLTea5Bv)'s #LearningCurves class.

**OVERVIEW OF PROGRAMMING LANGUAGE**

This programming language creates visual collage in the spirit of randomness. By returning unpredictable visual results, the language forces the user to think about the notion and definiting/definition in code. 

**DEADLINE**

__________________________________________________________________________________

October 17

*   [Moises Sanabria](/ep/profile/v6pSS8EP8fM)

        *   Have a small web app that calls the google api based on a text search.

October 24

*   [Moises Sanabria](/ep/profile/v6pSS8EP8fM)

        *   Able to parse text into seaprate searche.
    *   Maybe overlay images on top of each other.

**Reason**

*   I think the that the possibility of making this language is "doable".  I find the idea of writing poetry that compiles into visuals to be really interesting. It could also be an interesting way in which users could be introduced to programming from a meta point of view.

**Write User Instructions**

*   This is for the person who encounters this language in a website or gallery setting.
*   Have available example code that people can look at.

**Scope**

*   Recreate magic wand eraser and use it on searched image to get rid of background.

**Use Cases**

*   poetry night with dynamic live visuals compiled by the language listening to the poet?
*   introduction to mental models in computation?

**TECHNOLOGIES NEEDED**

*   Google Search API

        *   Custom Search API

                *   With this API, you can use RESTful requests to get either **web search** or **image search** results in JSON or Atom format.
        *   [](https://developers.google.com/custom-search/json-api/v1/overview)https://developers.google.com/custom-search/json-api/v1/overview

*   Wolfram-Alpha API
*   voice recognition API

        *   I started working with some voice recognition stuff over the weekend.  I forked the ofxSpeech addon, fixed it and added some new things.  It uses the speech recognition library built into OSX... we might be able to find a better tool?
    *   [](https://github.com/latrokles/ofxSpeech)https://github.com/latrokles/ofxSpeech

*   Node?
*   A way to write and parse the code
*   A large data set of images with transparent background? Maybe using ImageMagick to take the white off images? In terms of shapes we can create SVG masks on top of images in CSS3 to do something similar.

**MOCKUPS**

**Example 1:** Drawing the circle-triangle-rectangle

The canvas is 600px x 400px

        A circle should be on top of a triangle

                The circle could be orange

                The circle edges do not go beyond the triangle edges.

        The triangle is bigger than the circle.

        The triangle should be on top of a rectangle

                The triangle edges do not go beyond the rectangle edges

                The rectangle is bigger than the triangle

        The rectangle fills the canvas        

        All objects are centered

        ![](https://hackpad-attachments.s3.amazonaws.com/hackpad.com_Smv7hWK8gsV_p.77412_1380754811586_sketch-1.png)

        ![](https://hackpad-attachments.s3.amazonaws.com/hackpad.com_Smv7hWK8gsV_p.77412_1380754825987_sketch-2.png)

**Example 2:** If Statement

The background is the sky

        There is one circle

        If the circle is orange, draw a green square

                The green square should be the same width as the circle 

        Or else, draw a light blue line

                The line should be 2px wide and intersect two corners of the canvas

![](https://hackpad-attachments.s3.amazonaws.com/hackpad.com_Smv7hWK8gsV_p.77412_1380754905009_if-1.png)

![](https://hackpad-attachments.s3.amazonaws.com/hackpad.com_Smv7hWK8gsV_p.77412_1380754915199_if-2.png)

**Example 3**: For Loop

        The background is red

        For every triangle, draw two circles

                Triangles should be bigger than circles

                Triangles are on top of circles

                Circles are identical

        Draw five triangles

                Triangles are identical

                Triangles are centered

                Triangles are equally spaced vertically

![](https://hackpad-attachments.s3.amazonaws.com/hackpad.com_Smv7hWK8gsV_p.77412_1380754949541_for-loop.png)

**DOCUMENTATION**

__________________________________________________________________________________

**Programming Language Rules**

*   Canvas

        *   When nothing is specified the language randomly chooses a size for the canvas.
    *   It could also be the size of the largest image found.

*   Descriptors

        *   ex.

                *   The circle is blue / The circle should be blue.

    *

*   **Idea for IDE interface**