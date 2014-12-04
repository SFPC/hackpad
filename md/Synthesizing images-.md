# Synthesizing images!

   Zach's class... add your code!

  ------------------------------------------ 

   800x800 image

    for (int i = 0; i < myImg.getWidth(); i++){

        for (int j = 0; j < myImg.getHeight(); j++){

            pixels[ (int)(j * 800 + i)] = sin(i * j)  * 178.0 + 178.0;

        }

    }

    ![](https://hackpad-attachments.s3.amazonaws.com/hackpad.com_Sj61nBYJxjG_p.232391_1416242475748_Screen Shot 2014-11-17 at 11.39.45 AM.png)

-----------------------------

800 x 800 img

pixels[ (int)(j * 800 + i)] = (i - mouseX) * (j - mouseX) / 5.0;

![](https://hackpad-attachments.s3.amazonaws.com/hackpad.com_Sj61nBYJxjG_p.232391_1416242568872_Screen Shot 2014-11-17 at 11.42.34 AM.png)

----------------------------------

800 x 800 

  for (int i = 0; i < myImg.getWidth(); i++){

        for (int j = 0; j < myImg.getHeight(); j++){

            float distance = ofDist(i, j, mouseX, mouseY);

            if(distance < 200){

                pixels[ (int)(j * myImg.getWidth() + i)] = sin((i + j + 1) / 20.0) * 178.0 + 178.0;

            } else {

                pixels[ (int)(j * myImg.getWidth() + i)] = 0;

            }

        }

    }

![](https://hackpad-attachments.s3.amazonaws.com/hackpad.com_Sj61nBYJxjG_p.232391_1416243461210_Screen Shot 2014-11-17 at 11.57.02 AM.png)

  for (int i = 0; i < myImg.getWidth(); i++){

        for (int j = 0; j < myImg.getHeight(); j++){

                pixels[ (int)(j * myImg.getWidth() + i)] = sin((i +1) / 50.0) * 100.0 + cos((j +1) / 40.0) * 100.0 + 150.0;

        }

    }

![](https://hackpad-attachments.s3.amazonaws.com/hackpad.com_Sj61nBYJxjG_p.232391_1416244060816_Screen Shot 2014-11-17 at 12.07.08 PM.png)

                pixels[ (int)(j * myImg.getWidth() + i)] = (i - j)*(i+j);

             ![](https://hackpad-attachments.s3.amazonaws.com/hackpad.com_Sj61nBYJxjG_p.232391_1416251264520_Screen Shot 2014-11-17 at 2.06.34 PM.png)

                pixels[ (int)(j * myImg.getWidth() + i)] = (i/2.0 - j/2.0 + 5)*(i/3.0+j/1.0 + 100);

                ![](https://hackpad-attachments.s3.amazonaws.com/hackpad.com_Sj61nBYJxjG_p.232391_1416252757864_Screen Shot 2014-11-17 at 2.32.12 PM.png)

   k = rand() % 30 - 15;

            pixels[ (int)(j * myImg.getWidth() + i)] = (i/10.0 - j/10.0 + 5)*(i/10.0+j/10.0) + k;

            ![](https://hackpad-attachments.s3.amazonaws.com/hackpad.com_Sj61nBYJxjG_p.232391_1416253354882_Screen Shot 2014-11-17 at 2.42.02 PM.png)

Titled: "harvest the noise" (thanks Andrew!)

            k = rand() % 80 - 40;

            pixels[ (int)(j * myImg.getWidth() + i)] = (i/10.0 - j/10.0 + 5)*(i/10.0+j/10.0) + k;

           ![](https://hackpad-attachments.s3.amazonaws.com/hackpad.com_Sj61nBYJxjG_p.232391_1416253433442_Screen Shot 2014-11-17 at 2.43.05 PM.png)

    unsigned char * pixels = myImg.getPixels();

    float w = myImg.getWidth();

    for (float i = 0; i < myImg.getWidth(); i++){

        for (float j = 0; j < myImg.getHeight(); j++){

            k = rand() % 100;

            float norm = 255.0 / w;

            pixels[ (int)(j * w + i)] = i * norm + j * norm + k ;

        }

    }

    ![](https://hackpad-attachments.s3.amazonaws.com/hackpad.com_Sj61nBYJxjG_p.232391_1416253818031_Screen Shot 2014-11-17 at 2.49.54 PM.png)

        unsigned char * pixels = myImg.getPixels();

    float w = myImg.getWidth();

    for (float i = 0; i < myImg.getWidth(); i++){

        for (float j = 0; j < myImg.getHeight(); j++){

            k = rand() % 40;

            float norm = 255.0 / w;

            bool z = (int)((i - j)*(i+j)) % 255 > 220;

            if(z){

                pixels[ (int)(j * w + i)] = (i - j)*(i+j);

            } else {

                pixels[ (int)(j * w + i)] = 0;

            }

        }

    }

    ![](https://hackpad-attachments.s3.amazonaws.com/hackpad.com_Sj61nBYJxjG_p.232391_1416254341490_Screen Shot 2014-11-17 at 2.58.22 PM.png)

    unsigned char * pixels = myImg.getPixels();

    float w = myImg.getWidth();

    for (float i = 0; i < myImg.getWidth(); i++){

        for (float j = 0; j < myImg.getHeight(); j++){

            k = rand() % 40;

            float norm = 255.0 / w;

            bool z = (int)((i - j)*(i+j))% 255 < -230 ||(int)((i - j)*(i+j))% 255  > 230  ;

            if(z){

                pixels[ (int)(j * w + i)] = (i - j)*(i+j);

            } else {

                pixels[ (int)(j * w + i)] = 0;

            }

        }

    }

    ![](https://hackpad-attachments.s3.amazonaws.com/hackpad.com_Sj61nBYJxjG_p.232391_1416255179411_Screen Shot 2014-11-17 at 3.12.36 PM.png)

        for (float i = 0; i < myImg.getWidth(); i++){

        for (float j = 0; j < myImg.getHeight(); j++){

            if(rand() % 500 < 1) {

                pixels[ (int)(j * w + i)] = 255;

            } else {

                pixels[ (int)(j * w + i)] = 0;

            }

        }

    }

    ![](https://hackpad-attachments.s3.amazonaws.com/hackpad.com_Sj61nBYJxjG_p.232391_1416282367555_Screen Shot 2014-11-17 at 10.44.25 PM.png)

   for (float i = 0; i < myImg.getWidth(); i++){

        for (float j = 0; j < myImg.getHeight(); j++){

            if(rand() % 500 < 1) {

                pixels[ (int)(j * w + i)] = 255 - rand() % 200;

            } else {

                pixels[ (int)(j * w + i)] = 0;

            }

        }

    }

![](https://hackpad-attachments.s3.amazonaws.com/hackpad.com_Sj61nBYJxjG_p.232391_1416282556159_Screen Shot 2014-11-17 at 10.48.48 PM.png)

    Adding noise to define how likely it is that the given pixel will be a star pixel.  

            int val = ofNoise( i / 50.0, j / 50.0) * ofNoise( i / 500.0, j / 500.0) * 2000 + 1;

                if(rand() % val < 2) {

                        pixels[ (int)(j * w + i)] = 255 - rand() % 200;

                    } else {

                        pixels[ (int)(j * w + i)] = 0;

                    }

![](https://hackpad-attachments.s3.amazonaws.com/hackpad.com_Sj61nBYJxjG_p.232391_1416330395405_Screen Shot 2014-11-18 at 11.24.44 AM.png)

The underlying noise function is shown below... The darker pixels in the image below are more likely to be stars in the image above than the lighter areas. 

![](https://hackpad-attachments.s3.amazonaws.com/hackpad.com_Sj61nBYJxjG_p.232391_1416330591308_Screen Shot 2014-11-18 at 12.09.17 PM.png)

Using a the same noise function but with different parameters, we get a different star density.

  int val = ofNoise( i / 200.0, j / 200.0) * ofNoise( i / 100.0, j / 100.0) * 2000 + 1;

                if(rand() % val < 2) {

                        pixels[ (int)(j * w + i)] = 255 - rand() % 200;

                    } else {

                        pixels[ (int)(j * w + i)] = 0;

                    }

![](https://hackpad-attachments.s3.amazonaws.com/hackpad.com_Sj61nBYJxjG_p.232391_1416336453000_Screen Shot 2014-11-18 at 1.46.43 PM.png)![](https://hackpad-attachments.s3.amazonaws.com/hackpad.com_Sj61nBYJxjG_p.232391_1416336453011_Screen Shot 2014-11-18 at 1.45.38 PM.png)  