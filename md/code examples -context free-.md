# code examples (context free)

*   context free!

//------------------------------------------------

startshape HELLOMASTERMASTER

shape HELLOMASTERMASTER {

        HELLOMASTER[]

        HELLOMASTER[x 8 r 40]

}

shape HELLOMASTER {

   HELLO []

   HELLO [x 2]

   HELLO [x 4 r 20]

}

shape HELLO

{

  CIRCLE []

  SQUARE [x 1]  

  TRIANGLE [ y 1 ] 

}

//------------------------------------------------

startshape design

shape claw {

  loop 50 [ x 2.6 r 6 s 0.97 ] SQUARE [ ]

}

shape design {

  loop 8 [ r 45 ] claw [ ] 

}