---
layout: post
title: "Quick maps with R"
author: "Trey Batey"
date: "December 8, 2016"
categories: [spatial, rstats]
tags: [ggmaps, ggplot2]
---



Social scientists commonly need to visualize data across geographic space. Fortunately, R has many packages and functions for quickly producing vector and raster-based maps. For example, with just two short lines of code, we can produce a map of the United States.




{% highlight r %}
us <- get_map('usa', zoom = 3)
{% endhighlight %}



{% highlight text %}
## Source : https://maps.googleapis.com/maps/api/staticmap?center=usa&zoom=3&size=640x640&scale=2&maptype=terrain&language=en-EN
{% endhighlight %}



{% highlight text %}
## Source : https://maps.googleapis.com/maps/api/geocode/json?address=usa
{% endhighlight %}



{% highlight r %}
ggmap(us)
{% endhighlight %}

![plot of chunk unnamed-chunk-2](/socscistats/figure/source/2016-12-08-quick-maps-r/unnamed-chunk-2-1.png)
Or, we can use the `maps` package and display a vector map of the U. S.


{% highlight r %}
us2 <- map("usa")
{% endhighlight %}

![plot of chunk unnamed-chunk-3](/socscistats/figure/source/2016-12-08-quick-maps-r/unnamed-chunk-3-1.png)

{% highlight r %}
ggplot(data = us2, aes(x = long, y = lat)) + geom_polygon() 
{% endhighlight %}

![plot of chunk unnamed-chunk-3](/socscistats/figure/source/2016-12-08-quick-maps-r/unnamed-chunk-3-2.png)
