---
layout: post
title: "Quick maps with R"
author: "Trey Batey"
date: "December 8, 2016"
categories: [spatial, rstats]
tags: [ggmaps, ggplot2]
---



Social scientists commonly need to visualize data across geographic space. Fortunately, R has many packages and functions for quickly producing vector and raster-based maps.




{% highlight r %}
us <- get_map('usa', zoom = 4)
{% endhighlight %}



{% highlight text %}
## Source : https://maps.googleapis.com/maps/api/staticmap?center=usa&zoom=4&size=640x640&scale=2&maptype=terrain&language=en-EN
{% endhighlight %}



{% highlight text %}
## Source : https://maps.googleapis.com/maps/api/geocode/json?address=usa
{% endhighlight %}



{% highlight r %}
ggmap(us)
{% endhighlight %}

![plot of chunk unnamed-chunk-2](/socscistatsfigure/source/2016-12-08-quick-maps-r/unnamed-chunk-2-1.png)
