---
title: Indian Wells Visualization
layout: post
img: /img/tennis.png
---

Late saturday night/Sunday morning with everyone excited about the cricket match between
Pakistan and Ireland, I had an urge to check what was going on in the Tennis world. Knowing
Indian Wells had just started, I quickly needed to find who all my favourite players will be
playing. Looking at the draw and how outdated it looked I decided to have some with it.


### In comes D3
I have been meaning to dive in to D3 for quite some time but never really found 
a project or motivation to use it on. There are some really cool visualizations we can 
make using D3 but as a complete beginner I decided to follow a simple one given [here](https://gist.github.com/mbostock/4339083):


### The ugly part
Scraping the information needed for the draw wasn't as pretty as I hoped. Hoping there would be a csv or a text format
that I could use, I was clearly being too optimistic. But fortunately the website had the draw structured well enough that
I could use a little wget and Beautiful Soup to parse out and store the information as json.


### End Product
In the end it worked out all right. I even managed to get the scores out. Here is the final product [link](/tennisdraw/).
I'll definitely be getting more familiar with D3 and get more visualizations out there. You can check out the source
code right [here](https://github.com/faizanrashid/Visualize-Tennis)
