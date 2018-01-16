
# 100 Days Of Code - Log

### Day 1: January 2, 2018

**Today's Focus**: Begin learning [FSharp.Data](http://fsharp.github.io/FSharp.Data/) library.

**Details**:

 - Playing with [Html Type Provider](http://fsharp.github.io/FSharp.Data/library/HtmlProvider.html) to scrape Vikings episode information (seasons 1-3 in initial attempt) from Wikipedia.
 - Html Type Provider allows you to get compile time type safety and Intellisense from a live website (creates types behind the scenes and explores the HTML as you type)!
 - Great way to explore APIs.

**Examples**: Here is an example of the type provider in action, while it scrapes html information from the season 1 Wikipedia page. I'm able to access html, lists and tables on the fly and then access elements within those structures. Pretty neat stuff! [This](https://en.wikipedia.org/wiki/Vikings_(season_1)#Episodes) is the table I'm accessing from Wikipedia. Also, notice how useful the F# Interactive window is to test your code as your write it :open_mouth:

![Day 1 Example](https://github.com/jasondown/100-days-of-code/blob/master/images/day1_htmlprovide.gif)

**Link to work**: [Github](https://github.com/jasondown/FunWithFSharpData/)

----------
### Day 2: January 3, 2018

**Today's Focus**: Continue learning [FSharp.Data](http://fsharp.github.io/FSharp.Data/) library.

**Details**:

 - Refactored some of the Vikings episode Wikipedia scraper code. I figured out how to pass the [Html Type Provider](http://fsharp.github.io/FSharp.Data/library/HtmlProvider.html) as a parameter in a function so I could make some code reuse. Instead of instantiating one per season directly, I wrapped the type, providing the season 1 table as sample data. Then I used the *Load* function to create each season. Changes can be seen [here](https://github.com/jasondown/FunWithFSharpData/commit/0e79445abaa236e128384db03ff4080d425d7198) (*Note: There was a bug in the refactored code where all episodes were being reported as season 1. This has been fixed*).
 - Created another example using the [JSON Type Provider](http://fsharp.github.io/FSharp.Data/library/JsonProvider.html) and the free [IEX Trading API](https://iextrading.com/developer/docs/#getting-started) to grab a bunch of *tech giant* stock quote information and display the current trading price. Again, you get Intellisense from the JSON returned from the API.

**Examples**: Here is an animated GIF showing the stock quote code in use with F# Interactive:

![Day 2 Example](https://github.com/jasondown/100-days-of-code/blob/master/images/day2_jsonprovider.gif)

**Links to work**:

 - [Main repository](https://github.com/jasondown/FunWithFSharpData)
 - [Vikings episode scraper](https://github.com/jasondown/FunWithFSharpData/blob/master/FunWithFSharpData/HtmlProviderExample.fsx)
 - [Stock quote lookup](https://github.com/jasondown/FunWithFSharpData/blob/master/FunWithFSharpData/JsonProviderExample_StockQuotes.fsx)

----------
### Day 3: January 4, 2018

**Today's Focus**: Continue learning [FSharp.Data](http://fsharp.github.io/FSharp.Data/) library.

**Details**:

 - Looking at the [XML Type Provider](http://fsharp.github.io/FSharp.Data/library/XmlProvider.html) to get compile time safety for XML data (this may be useful for our translations stuff).
 -  I created a sample RSS reader to print N number of recent article summaries.
 - Also played with [partial function application](https://fsharpforfunandprofit.com/posts/partial-application/)... just because.
 - Making the example async would be interesting (might do that tomorrow). Also thinking about looking into actual unit testing (f# interactive is great for proof of concept and prototyping... which is also why I'm using fsharp script files instead of fsharp code files with proper modules/namespaces etc.).

**Examples**:

![Day 3 Example](https://github.com/jasondown/100-days-of-code/blob/master/images/day3_rssexample_xmlprovider.gif)

**Links to work**:

 - [Main repository](https://github.com/jasondown/FunWithFSharpData)
 - [RSS example](https://github.com/jasondown/FunWithFSharpData/blob/master/FunWithFSharpData/RssExample.fsx)


----------

