# Data Questions and Answers

Hi all - I'm working through people's questions in order of what I can answer quickest. Please add more questions or info as you want.

[motoishmz](/ep/profile/w4lbIML7ANO) Motoi's location data

My OpenPaths data (latest 100 records):

[](http://motoishmz-location.herokuapp.com/)http://motoishmz-location.herokuapp.com/ (html)

If you want to plot locations on a map, [](http://geojson.io/)http://geojson.io/ is AMAZING. LOOK:

*

[](https://gist.github.com/anonymous/93b24b7eb399011f8d7f)https://gist.github.com/anonymous/93b24b7eb399011f8d7f

 Steps to make this map in ~40 sec:

 1. Copy / Paste Motoi's location data into an OpenOffice spreadsheet

 2. Save the spreadsheet as a csv

 3. Drag the csv file onto the right hand side of [](http://geojson.io/)http://geojson.io/

 4. Click save

 5. Share the gist link!

 ***Next steps here: heatmap! Something actually interesting!

 -----------------------------------------------------------

 THE STORY OF JSON

 Collecting good json tools

*    mr data converter [](http://shancarter.github.io/mr-data-converter/)http://shancarter.github.io/mr-data-converter/
*   jsonlint json validator [](http://jsonlint.com/)http://jsonlint.com/

 json is a data format, like csv (comma separated values) or tsv (tab separated values)

 json has a lot of curly braces {} and brackets [] - when you see these in a data file, you're probably working with json

 json stands for "Javascript Object Notation" OBJECT is the most important part of that - json is good at describing OBJECTS. That's why data people like json.

 For instance! If I made a csv table of the data you're interested in it would look like this:

*   name, data, format, link
*   Motoi, location, csv, [](http://motoishmz-location.herokuapp.com/)http://motoishmz-location.herokuapp.com/
*   Motoi, location, json, [](http://motoishmz-location.herokuapp.com/locations.js)http://motoishmz-location.herokuapp.com/locations.js
*   Jonathan, Met, , [](http://scrapi.org/)http://scrapi.org/
*   Ishac, google searches, , 
*   Ishac, browser history, , 
*   Jason, OpenNI from a dancer, , 
*   Jason, Audio from a singer, , 
*   Tega, weather, json, [](https://developer.forecast.io/docs/v2)https://developer.forecast.io/docs/v2

If I use the AMAZING Mr. Data Converter [](http://shancarter.github.io/mr-data-converter/)http://shancarter.github.io/mr-data-converter/[ ](http://shancarter.github.io/mr-data-converter/to)to convert that to json, it looks like this:

*   [{"name":"Motoi"," data":" location"," format":" csv"," link":" [](http://motoishmz-location.herokuapp.com/)http://motoishmz-location.herokuapp.com/"},
*   {"name":"Motoi"," data":" location"," format":" json"," link":" [](http://motoishmz-location.herokuapp.com/locations.js)http://motoishmz-location.herokuapp.com/locations.js"},
*   {"name":"Jonathan"," data":" Met"," format":" "," link":" [](http://scrapi.org/)http://scrapi.org/"},
*   {"name":"Ishac"," data":" google searches"," format":" "," link":" "},
*   {"name":"Ishac"," data":" browser history"," format":" "," link":" "},
*   {"name":"Jason"," data":" OpenNI from a dancer"," format":" "," link":" "},
*   {"name":"Jason"," data":" Audio from a singer"," format":" "," link":" "},
*   {"name":"Tega"," data":" weather"," format":" json"," link":" [](https://developer.forecast.io/docs/v2)https://developer.forecast.io/docs/v2"}]

See? {} and [] everywhere. That's json.

If I put this json into the [](http://jsonlint.com/)http://jsonlint.com/ json validator and click "Validate" it formats it nicely, and tells me I have valid json. Now you can see better how json works - each line of a csv becomes an object in json. Every single piece of data comes with a name first, basically what would be the column name if the data were in a csv. (Scroll down and I'll tell you why we sometimes use json and not csv.)

[

    {

        "name": "Motoi",

        " data": " location",

        " format": " csv",

        " link": " [](http://motoishmz-location.herokuapp.com/)http://motoishmz-location.herokuapp.com/"

    },

    {

        "name": "Motoi",

        " data": " location",

        " format": " json",

        " link": " [](http://motoishmz-location.herokuapp.com/locations.js)http://motoishmz-location.herokuapp.com/locations.js"

    },

    {

        "name": "Jonathan",

        " data": " Met",

        " format": " ",

        " link": " [](http://scrapi.org/)http://scrapi.org/"

    },

    {

        "name": "Ishac",

        " data": " google searches",

        " format": " ",

        " link": " "

    },

    {

        "name": "Ishac",

        " data": " browser history",

        " format": " ",

        " link": " "

    },

    {

        "name": "Jason",

        " data": " OpenNI from a dancer",

        " format": " ",

        " link": " "

    },

    {

        "name": "Jason",

        " data": " Audio from a singer",

        " format": " ",

        " link": " "

    },

    {

        "name": "Tega",

        " data": " weather",

        " format": " json",

        " link": " [](https://developer.forecast.io/docs/v2)https://developer.forecast.io/docs/v2"

    }

]

So why don't we always just use csv? Why use json at all? One answer is NESTING. The thing is, it doesn't really make sense to have two lines of data for Motoi. It's redundant, and we HATE redundant data because it makes GIANT data files that are hard to work with. So, with json, we can change this:

[

    {

        "name": "Motoi",

        " data": " location",

        " format": " csv",

        " link": " [](http://motoishmz-location.herokuapp.com/)http://motoishmz-location.herokuapp.com/"

    },

    {

        "name": "Motoi",

        " data": " location",

        " format": " json",

        " link": " [](http://motoishmz-location.herokuapp.com/locations.js)http://motoishmz-location.herokuapp.com/locations.js"

    }

]

to this:

[

    {

        "name": "Motoi",

        " data": " location",

        "type": [

            {

                " format": " csv",

                " link": " [](http://motoishmz-location.herokuapp.com/)http://motoishmz-location.herokuapp.com/"

            },

            {

                " format": " json",

                " link": " [](http://motoishmz-location.herokuapp.com/locations.js)http://motoishmz-location.herokuapp.com/locations.js"

            }

        ]

    }

]

So now, there's just ONE Motoi, which makes sense, because he's just one man. He's interested in location data, and he provided two different types of location data.

We can do this in json, but not in csv - we're squishing two different things into the "type" cell.

(It took me a while to get all those {} and [] right - I ALWAYS use [](http://jsonlint.com/)http://jsonlint.com/ when I'm creating a json format from scratch, to make sure I'm actually making valid json.

Ok. So. json is important because almost all APIs will give you json.

Next up:  [Tega Brain](/ep/profile/ppZjvPL5nSC) Tega's data

FORECAST API - A set of weather data

I'd like to get data from this API: [](https://developer.forecast.io/)[https://developer.forecast.io/](https://developer.forecast.io/)

We'll practice working with APIs and json.

So you want to get data from an API? Step 1: Look at the docs! [](https://developer.forecast.io/docs/v2)https://developer.forecast.io/docs/v2

The first thing I notice in the docs is that I need an API key. I see that in the API call url:

[](https://api.forecast.io/forecast/APIKEY/LATITUDE,LONGITUDE)https://api.forecast.io/forecast/APIKEY/LATITUDE,LONGITUDE

Step 2: Register for a key!

(If you're following along, go and register for your own key here: [](https://developer.forecast.io/register))https://developer.forecast.io/register)

In this case, registering leads me to a page that shows me an example of my new API key being used to make a call to the API. (I'm taking out some of my key bc this is a public pad.)

Step 3: Save and protect your key! 

You'll need your key every time you use the API, and since there are a limited number of calls you can make per day (1000 in this case), you don't want other people using your key.

[](https://api.forecast.io/forecast/31f38d.........................06e5/37.8267,-122.423)https://api.forecast.io/forecast/31f38d[.](https://api.forecast.io/forecast/31f38d06e5/37.8267,-122.423).[.......................](https://api.forecast.io/forecast/31f38d..06e5/37.8267,-122.423)06e5/37.8267,-122.423

Step 4: Look at the docs again!

Now that we have a key, we can start fooling around with the API. This is a well documented API, which means that it lays out all the info about the calls to the API and what the API returns in plain English. This is not always the case. A well documented API makes us happy.

This API has two basic calls. The forecast call, which takes a lat, lon

[](https://api.forecast.io/forecast/APIKEY/LATITUDE,LONGITUDE)https://api.forecast.io/forecast/APIKEY/LATITUDE,LONGITUDE

and the forecast at a given time call, which takes lat, lon, time

[](https://api.forecast.io/forecast/APIKEY/LATITUDE,LONGITUDE,TIME)https://api.forecast.io/forecast/APIKEY/LATITUDE,LONGITUDE,TIME

Step 5: Experiment with some API calls! Notice the output.

Let's figure out the forecast at the school! I searched google for 33 Flatbush Ave, ask for the link to share, and the link has the lat, lon location of 40.797323,-74.1101. If I put this in the API call, like so (with my APIKEY filled in):

[](https://api.forecast.io/forecast/APIKEY/40.797323,-74.1101)[https://api.forecast.io/forecast/APIKEY/](https://api.forecast.io/forecast/APIKEY/LATITUDE,LONGITUDE)40.797323,-74.1101

I get this output in the browser: [Output of forecast.io API call for the schools location](/DR1PQEH3f4D)

boom! json. TOO MUCH JSON. 

[Tega Brain](/ep/profile/ppZjvPL5nSC) I think you're looking to get the time out at a given hour, so let's look at the output if we make a call for the school's location today at noon:

[](https://api.forecast.io/forecast/31f38.......06e5/40.797323,-74.1101,2013-11-04T12:00:00)https://api.forecast.io/forecast/31f38[.......](https://api.forecast.io/forecast/31f3806e5/40.797323,-74.1101,2013-11-04T12:00:00)06e5/40.797323,-74.1101,2013-11-04T12:00:00

Now I get this output in the browser: 

[Output of forecast.io for the schools location at a given time](/oMgWlLHBkks)

This is still WAY, WAY more data than Tega needs. We're interested in the data at the very top of the file, before the "hourly" starts. This part:

{"latitude":40.797323,"longitude":-74.1101,"timezone":"America/New_York","offset":-5,"currently":{"time":1383584400,"summary":"Clear","icon":"clear-day","precipIntensity":0,"precipProbability":0,"temperature":43.91,"apparentTemperature":40.19,"dewPoint":19.65,"windSpeed":6.38,"windBearing":45,"cloudCover":0.16,"humidity":0.37,"pressure":1036.14,"visibility":10,"ozone":262.22}

If I drop that into [](http://jsonlint.com/)http://jsonlint.com/ and click "Validate" I can see a nicer format:

{

    "latitude": 40.797323,

    "longitude": -74.1101,

    "timezone": "America/New_York",

    "offset": -5,

    "currently": {

        "time": 1383584400,

        "summary": "Clear",

        "icon": "clear-day",

        "precipIntensity": 0,

        "precipProbability": 0,

        "temperature": 43.91,

        "apparentTemperature": 40.19,

        "dewPoint": 19.65,

        "windSpeed": 6.38,

        "windBearing": 45,

        "cloudCover": 0.16,

        "humidity": 0.37,

        "pressure": 1036.14,

        "visibility": 10,

        "ozone": 262.22

    }

"time" should match what we asked for, which is:

2013-11-04T12:00:00

This "time": 1383584400 is unix time, which is measured as seconds since midnight GMT on 1 Jan 1970. You can use an online unix time converter to convince yourself that that's noon today, EST.

Step 6: Parse the data! 

We need to find a way to make a call to the API and get back *just* the data we need.

DRUMROLL.

THIS IS WHERE CODE COMES IN.

We want to be able to automate this process, to make repeated calls to the API and return the temperature, so we have to use CODE.

Forecast.io already has a bunch of wrappers written for it. [](https://developer.forecast.io/docs/v2)https://developer.forecast.io/docs/v2

We use a wrapper so that we don't have to parse the json ourselves. We could parse the json ourselves, because we are awesome and because there are libraries to help parse json in Python, R, Processing, etc. But the wrapper makes it super simple to get what we want. I'm going to use the Python one [](https://github.com/ZeevG/python-forcast.io)https://github.com/ZeevG/python-forcast.io, and then if I have time I'll work through a Processing json example.

*   ok. so. I need to install python-forecastio before I can use it, and my new machine doesn't have homebrew installed yet, so cue the hold music while I install homebrew [](http://brew.sh/)http://brew.sh/ (homebrew will help with installation of the python libraries)
**   What I'm doing on the command line:
*   $ ruby -e "$(curl -fsSL [](https://raw.github.com/mxcl/homebrew/go))[https://raw.github.com/mxcl/homebrew/go](https://raw.github.com/mxcl/homebrew/go))"
*   $ brew install python
*   (This is an insane detour I'm taking. I'm regretting this commitment to Python now.)

Ok! Python's up and running with pip to help us install libraries, so now let's get python-forecastio installed

$ pip install requests 

The python-forecast.io page told me it depends on requests, so I'm installing that. Here's the Requests python library, which is supposed to be great for API calls: [](http://docs.python-requests.org/en/latest/)http://docs.python-requests.org/en/latest/

$pip install python-forecastio

ack!! sickness!! I'll come back to this spot tomorrow and go from here

Super Cool!  Actually when you 'pip install python-forecastio' it should install requests for you.  This is specified in the setup.py file [](https://github.com/ZeevG/python-forcast.io/blob/master/setup.py)https://github.com/ZeevG/python-forcast.io/blob/master/setup.py