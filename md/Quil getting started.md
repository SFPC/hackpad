# Quil getting started

Quil is Clojure wrapper for Processing

[Github ](https://github.com/quil/quil)

**Install Leiningen**

"Leiningen is the easiest way to use [Clojure](http://clojure.org/). "

You need to install it also to use Quil.

[Official page ](http://leiningen.org/)

[Github](https://github.com/technomancy/leiningen)

1.  Copy the script from [here](https://raw.githubusercontent.com/technomancy/leiningen/stable/bin/lein) and saved with a name "lein".
2.  Then put on `/usr/bin/` folder on your Mac.  (make `$PATH` to `/usr/bin/`, means you can run lein by just type `lein` in Terminal)  
3.  You may need to change the permission by `$ chmod 755 /usr/bin/lein`.  
4.  Test with `$ lein -v`.  It shows a version if the install was successful

--- 

**Make a Quil project**

1. `$ lein new quil myapp`  //create a project

2. `$ cd myapp` //go inside the folder just created

3. `$ lein repl` //launch repl  

4. `user=> (require 'myapp.core :reload)` // *run the project  

*the location of the project is `src/myapp/core.clj` in this case.   

In repl, use `.` instead of `/` (not `myapp/core.clj` but `myapp.core`) 

![](https://hackpad-attachments.s3.amazonaws.com/hackpad.com_zYGDPTgodYz_p.257357_1416327250923_Screen%20Shot%202014-11-17%20at%2017.58.52.png)

There are many examples on github ([](https://github.com/quil/quil-examples))[https://github.com/quil/quil-examples](https://github.com/quil/quil-examples)). 

The tutorial on this page is helpful.