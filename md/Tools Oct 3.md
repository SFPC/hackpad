# Tools Oct 3

**Context Free Art**

Context free art - contextfreeart.org

*this is adorable [](http://www.contextfreeart.org/gallery/view.php?id=3520)http://www.contextfreeart.org/gallery/view.php?id=3520

*

code ex for square: *where 'x' is "shift over" & 's' is "size" & 'r' is "rotate"

*   startshape myCoolSquare
**   rule myCoolSquare {
*       SQUARE [size 2]
*       myCoolSquare [x 1.5 s 0.9 r 5

the curves / straight line example: 

*   startshape k
*    
*   background { h 90 sat 0 b -.7 }
*    
*   rule k {20*{x 1}{20*{y 1}A{ h 90 sat 0.7 b 1.0}}}
*   rule A{pa{}}
*   rule A{pa{r 90}}
*   rule A{pad{}}
*   rule A{pad{r 90}}
*    
*   path pa{
*   MOVETO{x 0 y -.5}
*   ARCTO{x -.5 y 0 r .5}
*   MOVETO{x 0 y .5}
*   ARCTO{x .5 y 0 r .5}
*   STROKE{width .2 p roundcap}
*   }
*    
*   path pad{
*   MOVETO{x -.5 y 0}
*   LINETO{x .5 y 0 }
*   STROKE{width .2 p roundcap}
*   }

This is the branching example: 

*   startshape myCoolNonSquare
**   rule myCoolNonSquare  {
*           CIRCLE [size 1]
*           fork { }
*   }
**   rule fork {
*           myCoolNonSquare [y 1.5 s 0.95 r 3]
*   }
**   rule fork 0.01 {
*           myCoolNonSquare  [y 1.5 s 0.95 rotate 1]
*           myCoolNonSquare  [y 2.5 s 0.95 rotate 320]
*   }
**   rule fork 0.1 {
*           myCoolNonSquare  [y 1.5 s 0.9 rotate 1]
*           myCoolNonSquare  [y 2.5 s 0.9 rotate 30]
*   }
*

**Nodebox**

[](http://nodebox.net/)http://nodebox.net/

*   nodebox 1 [](http://nodebox.net/code/index.php/Home)http://nodebox.net/code/index.php/Home
*   nodebox 3 [](http://nodebox.net/)http://nodebox.net/

*   size(500, 500)
**   # Set the background color to a specific hue of red
*   background(0.16, 0, 0)
**   # Set filling off, so ovals will be stroked only
*   nofill()
**   for i in range(10):
*       stroke(1.0, 1.0, 1.0, 1.0)
*       strokewidth(random(0.1, 0.4))
*       radius = random(40,900)
*       oval(random(WIDTH)-radius, random(HEIGHT)-radius, radius*2, radius*2)

spider example

*   # This example uses the points method to connect letters together.
*   # It actually draws lines between points of each letter contour
*   # that are a certain distance from eachother.
**   size(600, 207)
*   background(0.3,0,0.2)
**   # This utility method calculates the length between points.
*   # It's just a standard Pythagoras algorithm.
*   def calc_length(x1, y1, x2, y2):
*       from math import sqrt, pow
*       return sqrt(pow(x2-x1, 2) + pow(y2-y1, 2))
***   # First, create a textpath that we will use further on.
*   fontsize(150)
*   path = textpath("SFPC",20, 150)
**   # Select a color for the lines.
*   nofill()
*   stroke(1)
*   strokewidth(0.3)
**   # The mutation adds a little extra randomness to each calculated point.
*   # Increase it to make the lines deviate more from the template path.
*   mutation = 10.0
**   # The maximum distance between two points. Increase this to get a more
*   # "spidery" effect.
*   maxdist = 40.0
**   # Amount of lines for each contour.
*   lines_per_contour = 30
**   # A path has a contours property that returns each seperate contours.
*   # Note that "holes" in a letter (such as a P or D) are contours as well.
*   for contour in path.contours:
*       # Get a list of 100 points on each contour, properly divided amongst
*       # the path. This is different from the elements of the path, because
*       # the points are evenly distributed along the path.
*       path_points = list(contour.points(100))
*       
*       # We want a certain amount of lines.
*       for i in range(lines_per_contour):
*           # Choose a point on the path
*           pt1 = choice(path_points)
*           # To find the second point, we use a "brute-force" approach.
*           # We randomly select a point on the path, and see if its distance
*           # from the first point is smaller than the maximum allowed distance.
*           # If it is, the point is selected; otherwise, we try another point.
*           # Note that this might loop infinitely for very short (or negative) distances.
*           # Use Command-Period to break out of the loop.
*           
*           # Initialize the current length to "infinity", which means it won't get selected.
*           length = float("inf")        
*           while length > maxdist:
*               pt2  = choice(path_points) 
*               length = calc_length(pt1.x, pt1.y, pt2.x, pt2.y)
*               
*           # Once we've found a second point, draw it. Use the mutation parameter to add a bit
*           # of randomness to the position of the line.
*           line(pt1.x + random(-mutation, mutation), pt1.y + random(-mutation, mutation), \
*                pt2.x + random(-mutation, mutation), pt2.y + random(-mutation, mutation))
*             

**SuperCollider **

*    [](http://supercollider.sourceforge.net/)http://supercollider.sourceforge.net/
*    album made w 140 characters per song - [](http://supercollider.sourceforge.net/sc140/)http://supercollider.sourceforge.net/sc140/
*    supercollider code from in class: [](https://gist.github.com/ofZach/f64f27f03cd0e57b4434)https://gist.github.com/ofZach/f64f27f03cd0e57b4434
*   check out Nick Collins' info on his 12 week class, a lot of good info [](http://www.sussex.ac.uk/Users/nc81/modules/cm1/workshop.html)http://www.sussex.ac.uk/Users/nc81/modules/cm1/workshop.html

**Chuck**

*   [](http://chuck.cs.princeton.edu/)http://chuck.cs.princeton.edu/
*   examples from in class: [](https://github.com/ofZach/chuckExamples)https://github.com/ofZach/chuckExamples