# Source

The Crawling Search Party at Algolia

# tl;dr

## The challenges of crawling the web — and how to overcome them - [Samuel Bodin](https://www.linkedin.com/in/bodinsamuel/), [Algolia](https://www.algolia.com/)

+Use an ablocker when rendering crawled site to save resource and time.
+Be carefuk with query param, to avoir rendering multiple combination rewrite url to order them.
+ Put a hard limit on path concatenation to no blow up your crawler.
+ Trying to run your code in secure javascript engine will result in a huge perfomance trade off (x10).

## Automatic extraction of structured data from the Web - [Karl Leicht](https://www.linkedin.com/in/karl-leicht-208675104/), Fabriks

+ [Scrapy](https://scrapy.org/) is a nice python scrapper but it's not good with broad crawls of many domains.
+ [GoOse](https://github.com/advancedlogic/GoOse) is a nice tool to extract main content from a html page.
+ Don't forget when you extract data to also save version of the extractor used in order to rescrape it if you found bug later on extractor.
+Microdata is dead.

## Writing a distributed crawler architecture - [Nenad Tičarići](https://www.linkedin.com/in/nticaric), [TNT Studio](http://www.tntstudio.hr/)

+Presentation of their open source [crawler](https://github.com/teamtnt/crawler).

# Afterword



