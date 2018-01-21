
# 100 Days Of Code - Log
<a name="toc"></a>
### Table of Contents 
- [Day 1](#day-1) - **January 2, 2018** 
	- FSharp.Data, Html Type Provider
- [Day 2](#day-2) - **January 3, 2018**
	- FSharp.Data, Html Type Provider, JSON Type Provider, IEX Trading API
- [Day 3](#day-3) - **January 4, 2018**
	- FSharp.Data, XML Type Provider, RSS Feeds, Partial Function Application
- [Day 4](#day-4) - **January 5, 2018**
	- FSharp.Data, async, JSON Type Provider, IEX Trading API
- [Day 5](#day-5) - **January 6, 2018**
	- FSharp.Data, HTML Type Provider, FSharp.Charting, Bar Chart, BoxPlot Chart
- [Day 6](#day-6) - **January 7, 2018**
	- FSharp.Charting, RangeColumn Chart, Column Chart
- [Day 7](#day-7) - **January 8, 2018**
	- FsProjects/Mechanic open source project (F#)
- [Day 8](#day-8) - **January 9, 2018**
	- FSharp.Data, World Bank Type Provider, FSharp.Charting
- [Day 9](#day-9) - **January 10, 2018**
	- FsLab, OpenWeatherMap API, Google GeoChart, FSharp.Data, World Bank Type Provider
- [Day 10](#day-10) - **January 11, 2018**
	- FsLab, Google GeoChart, Deedle, FSharp.Data, Xml Type Provider
- [Day 11](#day-11) - **January 12, 2018**
	- F# Web Programming, Suave Framework
- [Day 12](#day-12) - **January 13, 2018**
	- F# Web Programming, Suave Framework
- [Day 13](#day-13) - **January 14, 2018**
	- F# Web Programming, Suave Framework, Star Wars API (SWAPI), F# Swapi, FSharp.Data, JSON Type Provider
- [Day 14](#day-14) - **January 15, 2018**
	- Codingame challenges, Classic Puzzles - Easy, Code Golf, Optimization, F#, C#
- [Day 15](#day-15) - **January 16, 2018**
	- Codingame challenges, Classic Puzzles - Easy, Scala, GitHub Markdown (this log)
- [Day 16](#day-16) - **January 17, 2018**
	- Codingame challenges, Classic Puzzles - Medium, F#
- [Day 17](#day-17) - **January 18, 2018**
	- Tidy, Tidy-Html5, TidyHtml5Managed, C#, C
- [Day 18](#day-18) - **January 19, 2018**
	- Codingame challenges, Classic Puzzles - Easy, Classic Puzzles - Medium, F#, C#
- [Dady 19](#day-19) - **January 20, 2018**
	- FSharp.Data, JSON Type Provider, Google APIs

----------
<a name="day-1"></a>
### Day 1: January 2, 2018 

**Today's Focus**: Begin learning [FSharp.Data](http://fsharp.github.io/FSharp.Data/) library.

**Details**:

 - Playing with [Html Type Provider](http://fsharp.github.io/FSharp.Data/library/HtmlProvider.html) to scrape Vikings episode information (seasons 1-3 in initial attempt) from Wikipedia.
 - Html Type Provider allows you to get compile time type safety and Intellisense from a live website (creates types behind the scenes and explores the HTML as you type)!
 - Great way to explore APIs.

**Examples**: Here is an example of the type provider in action, while it scrapes html information from the season 1 Wikipedia page. I'm able to access html, lists and tables on the fly and then access elements within those structures. Pretty neat stuff! [This](https://en.wikipedia.org/wiki/Vikings_(season_1)#Episodes) is the table I'm accessing from Wikipedia. Also, notice how useful the F# Interactive window is to test your code as your write it :open_mouth:

![Day 1 Example](https://github.com/jasondown/100-days-of-code/blob/master/images/day1_htmlprovide.gif)

**Link to work**: [Github](https://github.com/jasondown/FunWithFSharpData/)

[Table of Contents](#toc)

----------
 <a name="day-2"></a>
### Day 2: January 3, 2018

**Today's Focus**: Continue learning [FSharp.Data](http://fsharp.github.io/FSharp.Data/) library.

**Details**:

 - Refactored some of the Vikings episode Wikipedia scraper code. I figured out how to pass the [Html Type Provider](http://fsharp.github.io/FSharp.Data/library/HtmlProvider.html) as a parameter in a function so I could make some code reuse. Instead of instantiating one per season directly, I wrapped the type, providing the season 1 table as sample data. Then I used the *Load* function to create each season. Changes can be seen [here](https://github.com/jasondown/FunWithFSharpData/commit/0e79445abaa236e128384db03ff4080d425d7198). *NOTE: There was a bug in the refactored code where all episodes were being reported as season 1. This has been fixed*.
 - Created another example using the [JSON Type Provider](http://fsharp.github.io/FSharp.Data/library/JsonProvider.html) and the free [IEX Trading API](https://iextrading.com/developer/docs/#getting-started) to grab a bunch of *tech giant* stock quote information and display the current trading price. Again, you get Intellisense from the JSON returned from the API.

**Examples**: Here is an animated GIF showing the stock quote code in use with F# Interactive:

![Day 2 Example](https://github.com/jasondown/100-days-of-code/blob/master/images/day2_jsonprovider.gif)

**Links to work**:

 - [Main repository](https://github.com/jasondown/FunWithFSharpData)
 - [Vikings episode scraper](https://github.com/jasondown/FunWithFSharpData/blob/master/FunWithFSharpData/HtmlProviderExample.fsx)
 - [Stock quote lookup](https://github.com/jasondown/FunWithFSharpData/blob/master/FunWithFSharpData/JsonProviderExample_StockQuotes.fsx)


[Table of Contents](#toc)

----------
 <a name="day-3"></a>
### Day 3: January 4, 2018

**Today's Focus**: Continue learning [FSharp.Data](http://fsharp.github.io/FSharp.Data/) library.

**Details**:

 - Looking at the [XML Type Provider](http://fsharp.github.io/FSharp.Data/library/XmlProvider.html) to get compile time safety for XML data.
 -  I created a sample RSS reader to print N number of recent article summaries.
 - Also played with [partial function application](https://fsharpforfunandprofit.com/posts/partial-application/)... just because.
 - Making the example async would be interesting (might do that tomorrow). Also thinking about looking into actual unit testing (f# interactive is great for proof of concept and prototyping... which is also why I'm using fsharp script files instead of fsharp code files with proper modules/namespaces etc.).

**Examples**:

![Day 3 Example](https://github.com/jasondown/100-days-of-code/blob/master/images/day3_rssexample_xmlprovider.gif)

**Links to work**:

 - [Main repository](https://github.com/jasondown/FunWithFSharpData)
 - [RSS example](https://github.com/jasondown/FunWithFSharpData/blob/master/FunWithFSharpData/RssExample.fsx)

[Table of Contents](#toc)

----------
 <a name="day-4"></a>
### Day 4: January 5, 2018

**Today's Focus**: Continue learning [FSharp.Data](http://fsharp.github.io/FSharp.Data/) library. Also look into async programming in F#.

**Details**:

 - Explored the [async workflow](https://docs.microsoft.com/en-us/dotnet/fsharp/language-reference/asynchronous-workflows) in F#.
 - There are two ways to use Async, via an *asyc { ... }* block or using *Async.Methods*. I opted for the latter this time around.
 - Updated the [JSON Type Provider](http://fsharp.github.io/FSharp.Data/library/JsonProvider.html) (using the free [IEX Trading API](https://iextrading.com/developer/docs/#getting-started) to grab a bunch of tech giant stock quote information and display the current trading price) to load each stock quote asynchronously and then display them all at the end. I could try displaying them as they come back, but then I couldn't sort them by price descending.
 - I also discovered the *#time* timer in F# interactive. I used it to compare the sync vs async versions of my code. I looped the stock quotes 10 times (twice for each type) and it was consistently faster with the async version.
 - Lost internet for about two hours last night :angry:

**Examples**: This animated GIF shows comparing the two approaches:

![Day 4 Example](https://github.com/jasondown/100-days-of-code/blob/master/images/day4_rssexample_async.gif)

**Links to work**:

- [Main repository](https://github.com/jasondown/FunWithFSharpData)
- [Rss example with sync/async loading](https://github.com/jasondown/FunWithFSharpData/blob/master/FunWithFSharpData/JsonProviderExample_StockQuotes.fsx)

[Table of Contents](#toc)

----------
<a name="day-5"></a>
### Day 5: January 6, 2018 

**Today's Focus**: Begin learning [FSharp.Charting](https://fslab.org/FSharp.Charting/index.html) and combine it with [FSharp.Data](http://fsharp.github.io/FSharp.Data/) library. 

**Details**:

 - Used the [HTML Type Provider](http://fsharp.github.io/FSharp.Data/library/HtmlProvider.html) to scrape Wikipedia for [PGA Tour Major winners](https://en.wikipedia.org/wiki/List_of_men%27s_major_championships_winning_golfers#By_golfer)  (Name, total wins and winning span (first to last major win year)).
 - Used the [FSharp.Charting Bar Chart](https://fslab.org/FSharp.Charting/BarAndColumnCharts.html) to display total major wins (you pass in the minimum wins to be included to keep the number of golfers down so the chart doesn't have way too many people on one axis). *NOTE: The bar chart documentation was a bit messed up, so it took some playing around to figure things out.*
 - ***Abused*** the [FSharp.Charting.BoxPlot Chart](https://fslab.org/FSharp.Charting/BoxPlotCharts.html) which is normally used for statistics (six statistics with lower whisker, upper whisker, lower box, upper box, average and median). I just like that it looked like a range chart, so manipulated the golfer major winning span years to work with the chart. It worked out pretty well!

**Examples**: Here are the two charts in action:

![Day 5 Example - Total Wins](https://github.com/jasondown/100-days-of-code/blob/master/images/day5_total_wins.png)

![Day 5 Example - Winning Span](https://github.com/jasondown/100-days-of-code/blob/master/images/day5_winning_span.png)

**Links to work**:

 - [Main repository](https://github.com/jasondown/FunWithFSharpData)
 - [Charting Code](https://github.com/jasondown/FunWithFSharpData/blob/master/FunWithFSharpData/GolfMajors.fsx)

[Table of Contents](#toc)

----------
<a name="day-6"></a>
### Day 6: January 7, 2018 

**Today's Focus**: Continue learning [FSharp.Charting](https://fslab.org/FSharp.Charting/index.html) and refactoring the golf major championship charting code.

**Details**:

 - Discovered the [FSharp.Charting.RangeColumn](https://fslab.org/FSharp.Charting/reference/fsharp-charting-chart.html) (and Range) chart. I had to find it in the main API page since they didn't have a link and example to it like some of the other chart types.
 - Updated the golf major championship winners script to use the RangeColumn chart, which simplified the code  over the original BoxPlot chart I used yesterday.
 - Refactored the code to more easily adjust the parameters and charts dynamically. 
 - Discovered you can use stuff like Label = ["#VALY, #VALY2"](https://msdn.microsoft.com/en-us/library/dd456687.aspx) to label values based on the data for each record. Unfortunately you can't do expressions on them (like "#VALY2" - "#VALY" to get the total years between the end and beginning date).

**Examples**: Here are the updated charts:

![Day 6 Example - Total Wins](https://github.com/jasondown/100-days-of-code/blob/master/images/day6_total_wins.png)

![Day 6 Example - Winning Span](https://github.com/jasondown/100-days-of-code/blob/master/images/day6_winning_span.png)

**Links to work**:

 - [Main repository](https://github.com/jasondown/FunWithFSharpData)
 - [Charting Code](https://github.com/jasondown/FunWithFSharpData/blob/master/FunWithFSharpData/GolfMajors.fsx) 

[Table of Contents](#toc)

----------
 <a name="day-7"></a>
### Day 7: January 8, 2018

**Today's Focus**: I joined the F# open source community tonight via the [FsProjects/Mechanic](https://github.com/fsprojects/Mechanic) project on GitHub. 

This project is aimed at getting some new comers to the F# OSS community with mentoring and guidance from some very talented developers like [Steffen Forkmann](https://github.com/forki) (creator of [Paket](https://fsprojects.github.io/Paket/)) and [Krzysztof Cieślak](https://github.com/Krzysztof-Cieslak) (creator of the [Ionide](http://ionide.io/) plugin for f# cross-platform development in Visual Studio Code).

**Details**: I'll be learning the following tool chain to go along with F#:

 - [Paket](https://fsprojects.github.io/Paket/index.html) - Dependency management.
 - [Fake](https://fake.build/) (F# Make) - An F# DSL for build tasks and more.
 - [DotNet CLI](https://github.com/dotnet/cli/) - Command line tools for .Net Core.
 - [GitVersion](https://github.com/GitTools/GitVersion) - Easy semantic versioning for projects using GitHub.
 - [FsCheck](https://fscheck.github.io/FsCheck/) - Property based testing (based on Haskell Quickcheck).
 - [Expecto](https://github.com/haf/expecto) - A testing library for F#.

I spent most of my time on getting the repository forked and built and then exploring the project. I even made my first pull request, which was accepted. **Woo!** It was just fixing a link in the readme, but you gotta start somewhere.

![Giphy - Jedi Training](https://github.com/jasondown/100-days-of-code/blob/master/images/day7.gif)

**Link to work**: [Github](https://github.com/jasondown/Mechanic)

[Table of Contents](#toc)

----------
 <a name="day-8"></a>
### Day 8: January 9, 2018

**Today's Focus**: Returned to learning [FSharp.Charting](https://fslab.org/FSharp.Charting/index.html) and [FSharp.Data](http://fsharp.github.io/FSharp.Data/) libraries.

 **Details**:
 
 - Explored the [World Bank Type provider](http://fsharp.github.io/FSharp.Data/library/WorldBank.html):
	 >The World Bank is an international organization that provides financial and technical assistance to developing countries around the world. As one of the activities, the World Bank also collects development indicators and other data about countries in the world. The data catalog contains over 8,000 indicators that can be programmatically accessed.
 - *NOTE: There are a lot of indicators, so the Intellisense can take a couple seconds to pop up initially.*
 - Used the async version of the type provider to load multiple indicators for multiple countries at once.
 - Used FSharp.Charting again to draw some interesting charts for displaying the data.
 - Used the new .Net underscore separator so large integer constants are easier to read:
	 -  *50_000_000 vs 50000000 is much easier to tell you are talking about 50 million.*

**Examples**: The final result of playing around was to load the total population, female population and male population of Canada, the US and the UK and display them in comparison charts. Not too shabby for relatively little code.

![Day 8 - Population Charts](https://github.com/jasondown/100-days-of-code/blob/master/images/day8_populations.png)

**Links to work**: 

 - [Main repository](https://github.com/jasondown/FunWithFSharpData)
 - [World Bank Type Provider and Charting Code](https://github.com/jasondown/FunWithFSharpData/blob/master/FunWithFSharpData/WorldBankProvider.fsx)

[Table of Contents](#toc)

----------
 <a name="day-9"></a>
### Day 9: January 10, 2018

**Today's Focus**: [Analyzing and Visualizing Data With F#](https://www.oreilly.com/ideas/analyzing-and-visualizing-data-with-f-sharp) (book by Tomas Petricek). The first chapter was a nice mix of stuff I've already been playing with and new stuff.

 **Details**: The following technologies were used:

 - [OpenWeatherMap API](https://www.oreilly.com/ideas/analyzing-and-visualizing-data-with-f-sharp) (I already had an api key when I was reading [Elixir and OTP](https://www.manning.com/books/the-little-elixir-and-otp-guidebook) a while ago. Who knew!?!)
 - [FsLab](https://fslab.org/)
 - [World Bank Type Provider](http://fsharp.github.io/FSharp.Data/library/WorldBank.html)
 - [Google GeoChart](https://developers.google.com/chart/interactive/docs/gallery/geochart)

The idea was to:

 - Use the World Bank type provider to get a list of capital cities in the world.
 - Take that list and feed it into a chain of calls to the OpenWeatherMap API to get the high temperature for tomorrow's forecast (in degrees Celsius).
 - I had to work some F# magic to handle capital cities that weren't listed in the OpenWeatherMap API for some reason (e.g. Washington D.C. ... strange).
 - Feed the list of cities into the Google GeoChart and configure it for some pretty colours to show the temperature.

*Caveat: The temperature for an entire country is based on the temperature in the capital city. Obviously, that is not very accurate. At this time of night, what are you gonna do?* 

Unfortunately, if a city didn't come back with a temperature, the temperature was not set and that country is greyed out. Oh well.

**Examples**:

![Day 9 Example - GeoChart](https://github.com/jasondown/100-days-of-code/blob/master/images/day9_geochart.gif)

**Links to work**: 

 - [Main repository](https://github.com/jasondown/FunWithFSLab)
 - [OpenWeatherMap API and GeoChart Code](https://github.com/jasondown/FunWithFSLab/blob/master/OpenWeather.fsx)

[Table of Contents](#toc)

----------
 <a name="day-10"></a>
### Day 10: January 11, 2018

**Today's Focus**:  Continued with the book [Analyzing and Visualizing Data With F#](https://www.oreilly.com/ideas/analyzing-and-visualizing-data-with-f-sharp) by Tomas Petricek. The second chapter introduced some new stuff from [FsLab](https://fslab.org/).

 **Details**:

 - Began looking at the [Deedle](http://bluemountaincapital.github.io/Deedle/) exploratory library.
	 >Deedle is an easy to use library for data and time series manipulation and for scientific programming. It supports working with structured data frames, ordered and unordered data, as well as time series. Deedle is designed to work well for exploratory programming using F# and C# interactive console, but can be also used in efficient compiled .NET code.
 - I combined Deedle with the World Bank API again (this time accessed through the [XML Type Provider](http://fsharp.github.io/FSharp.Data/library/XmlProvider.html) rather than the [World Bank Type Provider](http://fsharp.github.io/FSharp.Data/library/WorldBank.html)).
 - Looked up various indicators for all countries, for specific years or date ranges.
 - Showed data in a [Google GeoChart](https://developers.google.com/chart/interactive/docs/gallery/geochart).
 - Showed data in a Deedle Frame (think table displayed in F# Interactive).

I stopped about 3/4 of the way through chapter 2 before getting into the R Type Provider (requires installing R, but gives you access to R charts/plots, statistics etc. directly in F#).

**Examples**: Nothing too fancy to show tonight in a gif (couple more geo charts, which I won't show). This is an example of a section of a Deedle Frame showing a bunch of indicators from the World Bank for 2012 (lots of values start to be missing as you get more recent for some of these things). With R and the R Type provider, I could plot some cool diagrams and find possible correlations between indicators. One day...

![Day 10 Example - Deedle Frame](https://github.com/jasondown/100-days-of-code/blob/master/images/day10_deedleframe.gif)

**Links to work**: 

 - [Main repository](https://github.com/jasondown/FunWithFSLab)
 - [Deedle Code](https://github.com/jasondown/FunWithFSLab/blob/master/DeedleExample.fsx)

[Table of Contents](#toc)

----------
<a name="day-11"></a>
### Day 11: January 12, 2018

**Today's Focus**:  Web programming in F# using the [Suave](https://suave.io/) framework.

 **Details**:

 - Exploring [Sauve](https://suave.io)
	 >Suave is a simple web development F# library providing a lightweight web server and a set of combinators to manipulate route flow and task composition.
 - Started with GET and POST implementations for people (I guess similar to a controller, but less bloat).
 - I'll admit, at first the syntax was weird, even for F#. Then I realized that they just built a little DSL to easily compose things together (combinators) via a **>=>** operator. It looks even crazier with my FiraCode font and ligatures:

![Day 11 - Ligatures](https://github.com/jasondown/100-days-of-code/blob/master/images/day11_ligatures.jpg)

I've been following along with [this tutorial](http://blog.tamizhvendan.in/blog/2015/06/11/building-rest-api-in-fsharp-using-suave/) (some slight mods have to be made because the library has been changed slightly since the tutorial was written).

**Examples**: Here are some Postman screenshots of the POST and GET requests:

![Day 11 Example - POST](https://github.com/jasondown/100-days-of-code/blob/master/images/day11_postsuave.png)

![Day 11 Example - GET](https://github.com/jasondown/100-days-of-code/blob/master/images/day11_getsuave.png)

**Link to work**: [GitHub](https://github.com/jasondown/FunWithSuave)

[Table of Contents](#toc)

----------
<a name="day-12"></a>
### Day 12: January 13, 2018

**Today's Focus**:  Continued web programming in F# via the [Suave](https://suave.io/) framework.

 **Details**:
 
 - Moved forward with the [tutorial](http://blog.tamizhvendan.in/blog/2015/06/11/building-rest-api-in-fsharp-using-suave/) from yesterday. Today it clicked completely after seeing more of the code, which just made it that much cooler to me.
 - Added the HTTP PUT (with some error handling for missing resources) and HTTP DELETE implementations (again, both implemenations are for people in a "database" (read: in memory Dictionary)).

**Examples**: Postman screenshots below.

HTTP GET - Just to show the dataset that was created via HTTP POST:

![Day 12 Example - HTTP GET](https://github.com/jasondown/100-days-of-code/blob/master/images/day12_getsuave.png)

HTTP PUT - To change Yoda's name:

![Day 12 Example - HTTP PUT](https://github.com/jasondown/100-days-of-code/blob/master/images/day12_putsuave.png)

HTTP PUT - Error handling for missing resources. *This is not the captain you're looking for*:

![Day 12 Example - HTTP PUT With Error Handling](https://github.com/jasondown/100-days-of-code/blob/master/images/day12_put_no_resource_suave.png)

HTTP DELETE - Not much to see here, other than the 204 status (people/3 was Darth Vader, who was [erased from existence](https://youtu.be/WAQbRFZU7rE?t=12s)):

![Day 12 Example - HTTP DELETE](https://github.com/jasondown/100-days-of-code/blob/master/images/day12_delete_suave.png)

**Link to work**: [GitHub](https://github.com/jasondown/FunWithSuave)

[Table of Contents](#toc)

----------
<a name="day-13"></a>
### Day 13: January 14, 2018

**Today's Focus**:  As I learn new things ([Suave](https://suave.io) framework), I like to combine the *new hotness* with recent things I learned to make sure I cement those ideas into my noggin... Ok, that word immediately brings some [flash backs](https://youtu.be/t-OCjvbV2Z4?t=8s). 

![It's Like an Orange on a Toothpick](https://github.com/jasondown/100-days-of-code/blob/master/images/day13.gif)

 **Details**:

 - Today I continued working with the [Suave](https://suave.io/) framework to finish [this tutorial](http://blog.tamizhvendan.in/blog/2015/06/11/building-rest-api-in-fsharp-using-suave/). There were a few new commands added making use of HTTP HEAD etc. to see if a record exists.
 - Taking some motivation from the React sessions put on a couple coworkers about 6 months ago, I used the [Star Wars API](https://swapi.co/) (SWAPI) to populate my "database" (dictionary) on start up with characters from Star Wars. 
 - I explored the code from Evelina Gabasova's [F# Swapi](https://github.com/evelinag/fsharp-swapi) library to nicely integrate the Star Wars API into the code via the [F# JSON Type Provider](http://fsharp.github.io/FSharp.Data/library/JsonProvider.html).
 - I also modified the original tutorial code a bit to better fit the data types returned by the SWAPI.
 - Lastly, I did some refactoring of the original tutorial code.

**Examples**: Here is Postman in action, loading all the SW characters and a single one:

![Day 13 Example - Star Wars API and Suave](https://github.com/jasondown/100-days-of-code/blob/master/images/day13_sauve_star_wars.gif)

**Link to work**: [GitHub](https://github.com/jasondown/FunWithSuave)

[Table of Contents](#toc)

----------
<a name="day-14"></a>
### Day 14: January 15, 2018

**Today's Focus**: Tonight I decided to do some [Codingame](https://codingame.com/) puzzles.

**Details**:

 - I created a new repository to hold my solutions (for anything except for contests, since they don't like you to do that).
 - I tossed up all my *Classic Puzzle - Easy* solutions for C# and F#. A couple things I noticed:
	 - I realized I hadn't solved all of them in both languages. I'll be doing that soon.
	 - My C# code from some of the older solutions I did a couple of years ago look a little different from how I'd do them today.
 - I also tossed up one of my *code golf* solutions (F#... which will beat C# for size, but no chance against the python solutions).
 - Finally, I started looking into one of the *optimization* challenges (Code vs Zombies). That's just a shell right now with the default code for the F# solution.

Plans for the rest of the week:
 - Finish the four *Classic Puzzle - Easy* challenges I missed (2 for F# and 2 for C#... not the same ones mind you).
 - Get some more *code golf* challenges up (probably just F#).
 - Finish my Code vs Zombies solution.
 - Time permitting, I'll do some more optimization puzzles.
 - If I'm feeling really ambitious, I'll start going at the *Classic Puzzle - Medium* challenges (I have a couple done already in both C# and F#).
 - In the distant future (before my 100 days are up), I'll do some of the puzzles in another language or two (leaning towards Scala first).

Also, after 2 weeks, here is how my github contributions are looking. Unfortunately, on the first day and the fourth day I made all my commits just after midnight, so they look like they were part of day 2 and day 5. Mind the gap!

![Day 14 - Progress on contributions](https://github.com/jasondown/100-days-of-code/blob/master/images/day14.jpeg)

**Link to work**: [GitHub](https://github.com/jasondown/codingame)

[Table of Contents](#toc)

----------
<a name="day-15"></a>
### Day 15: January 16, 2018

**Today's Focus**: Continued with some [Codingame](https://codingame.com/) puzzles.

**Details**:

 - Decided to do three *Classic Puzzle - Easy* solutions in Scala. It was similar enough to F# for me to get the gist of it, but different enough that I had to do some research.
 - I don't know much about the JVM (haven't programmed in Java in over 15 years!), but Scala seems pretty cool.
 - I may need to explore Clojure a little more now too (I hear there is a Clojure for the .Net CLR too). I do like me some LISP.

As an added bonus the past couple of days, I have been creating this log on GitHub. I'm finally caught up today (my logs were being created on an internal platform where I work before I discovered this repository and forked it).

Also, I was listening to this cool [Scandroid](https://scandroid.bandcamp.com/album/scandroid) (Cyberpunk genre) album tonight while working. I recommend it!

**Link to work**: [GitHub](https://github.com/jasondown/codingame)

[Table of Contents](#toc)

----------
<a name="day-16"></a>
### Day 16: January 17, 2018

**Today's Focus**: Continued with some [Codingame](https://codingame.com/) puzzles.

**Details**:

- Added two *Classic Puzzle - Medium* solutions in F#: War (the card game) and Don't Panic ([HHGTTG](https://en.wikipedia.org/wiki/The_Hitchhiker%27s_Guide_to_the_Galaxy) reference)
- The solutions are very domain logic centric (overkill for these solutions, but something that's more enterprisey like).
- I attempted a third puzzle (trying to be overly clever). Failed miserably. I'll make another attempt at it tomorrow, likely without trying to be *clever*.

**Link to work**: [GitHub](https://github.com/jasondown/codingame)

[Table of Contents](#toc)

----------
<a name="day-17"></a>
### Day 17: January 18, 2018

**Today's Focus**: 100 Days of code is now merging with some work related interests. I've decided to update the TidyHtml5Managed wrapper library around Tidy (or HTML Tidy... or HTML Tidy 5) to the newest version and update the nuget package. I'd also like to make sure the XML documentation is part of the NuGet package.

**Details**

- Original managed library was created by Mark Beaton [here](https://github.com/markbeaton/TidyManaged).
- Updates were made by Frandi Dwi to drop support for the old version of Tidy and support version 5.0. [here](https://github.com/frandi/TidyHtml5Managed). Support for versions of .Net from 2.0 through 4.5 were also added.
- More updates were made by gabrieleteotino to support 32 bit and 64 bit versions [here](https://github.com/gabrieleteotino/TidyHtml5Managed). The supported version of Tidy was also updated to 5.2.
- Original Tidy library (C version) was found [here](http://tidy.sourceforge.net/).
- New versions of Tidy (C version) are now maintained [here](http://www.html-tidy.org/) (and source code is [here](https://github.com/htacg/tidy-html5)).
- I've forked the managed repository (seems to no longer be maintained) and fixed some links. I plan to update to the latest version of Tidy (5.6 at the moment) and add the necessary PInvoke calls for any new features.
- I also plan to create an updated NuGet package and ensure that the XML documentation is included (currently this is not the case in [this](https://www.nuget.org/packages/TidyHtml5ManagedRepack/) package or [this](https://www.nuget.org/packages/TidyHtml5Managed/) package).

**Link to work**: [GitHub](https://github.com/jasondown/TidyHtml5Managed)

[Table of Contents](#toc)

----------
<a name="day-18"></a>
### Day 18: January 19, 2018

**Today's Focus**: Continued with some [Codingame](https://codingame.com/) puzzles.

**Details**:

- Added a *Classic Puzzle - Medium* solution in F#: Stock Exchange Losses.
- Added a *Classic Puzzle - Easy* solution in C#: The Descent.

**Link to work**: [GitHub](https://github.com/jasondown/codingame)

[Table of Contents](#toc)

----------
----------
 <a name="day-19"></a>
### Day 4: January 5, 2018

**Today's Focus**: Looking for some APIs to play with so made use of [FSharp.Data](http://fsharp.github.io/FSharp.Data/) library for discovery.

**Details**:

 - Used the [JSON Type Provider](http://fsharp.github.io/FSharp.Data/library/JsonProvider.html) to get a list of Google APIs.
 - Converted the JSON responses to summary objects with title, description and documenation links.
 - Converted the summaries into an HTML file with a table (rather ugly, but I was not going for a nice design).

**Examples**: This is a screen shot of my fugly html file:

**Links to work**: 

 - [Main repository](https://github.com/jasondown/FunWithFSharpData)
 - [Google API Discovery and HTML Page Generator](https://github.com/jasondown/FunWithFSharpData/blob/master/FunWithFSharpData/GoogleApis.fsx)

[Table of Contents](#toc)

----------
