# DataVis with Jen

When looking for data behind data visualisations. 

Use google developer tools and open the html of the site.

*   In the html we are looking for links to the json files or equivalent to find the data used in the visualisations. 
*   Looking at the peoplemovin website. 
*   Look for json but if there is none.
*   look at javascript files. 
*   In the javascript there is a php script to connect to some json files in this example.
*   This takes us to the data.

JSON TOOLS

JSON Validators are really useful for checking JSON files. 

*   [www.jsonlint.com](http://www.jsonlint.com) is really useful for this.
*   [](http://shancarter.github.io/mr-data-converter/)http://shancarter.github.io/mr-data-converter/

Binning 

*   Taking a dataset and dividing it up into bins (or sections). It means a person has selected where the important distinctions in the data. It is a way that data cab be manipulated (for good or evil). 

*   How does data visualisation obscure the assumptions upon which it is based?

Working with APIs

*   Some are well documented, some are not. 
*   Looking at forecast.io
*   An API call - this is an call that will return a slice of the data to you, you can type this into your browser and the data will be returned to you. 
*   You are requesting just a slice of the data from the database. 

Python is great for working with data- it has a good community and history. 

*   Python wrapper libraries have been written for many APIs. 
*   The forecast API, has a few python wrappers
*   PIP is a thing that takes care of the installation for you. 
*   If you can avoid downloading zips of python and installing AVOID THIS!
*   PIP is a thing that will manage the installation of the python stuff for you. Saves you a lot of complications of the manual installation. 

Using Python with Homebrew.

5 STEPS FOR WORKING WITH PYTHON WITHOUT LOSING YOUR MIND

*   go to the homebrew webpage.
*   Install homebrew
*   Install python: $brew install python
*   *change the path for python - you may or may not need to do this - use if pip isn't found* 
*   $nano .bash_profile
*   add this line to your .bash_profile: export PATH=/bin:/usr/local/bin:$PATH
*   save your .bash_profile
*   Now you can install using "pip install" to install python libraries

pip install requests

pip install python-forecastio

Sublime Text + Python

Save this as test.py in SublimeText:

import requests

import forecastio

print 'hello python!'

api_key = "31f38d07c51ba765afceb5189f2906e5"

lat = -31.967819

lng = 115.87718

forecast = forecastio.load_forecast(api_key, lat, lng)

byHour = forecast.hourly()

print byHour.summary

Hit Command-B - it should run......

TERMINAL STUFF

*   if you have a giant file that you cannot open, you can use the terminal to type head and the file name and it will just open the file header. 

        *   likewise "tail" which opens the end

*