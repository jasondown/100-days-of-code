
# 100 Days Of Code - Log
<a name="toc"></a>
### Table of Contents 
- [Day 1](#day-1) - **January 2, 2018** 
	- Focus: FSharp.Data
- [Day 2](#day-2) - **January 3, 2018**
	- Forcus: FSharp.Data
- [Day 3](#day-3) - **January 4, 2018**
	- Focus: FSharp.Data
- [Day 4](#day-4) - **January 5, 2018**
	- Focus: FSharp.Data, async
- [Day 5](#day-5) - **January 6, 2018**
	- Focus: FSharp.Data, FSharp.Charting
- [Day 6](#day-6) - **January 7, 2018**
	- Focus: FSharp.Charting
- [Day 7](#day-7) - **January 8, 2018**
	- Focus: FsProjects/Mechanic open source project (F#)

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

