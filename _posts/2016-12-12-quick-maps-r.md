---
layout: post
title: "Quick maps with R"
author: "Trey Batey"
date: 2016-12-12
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

<img src="/socscistats/figure/source/2016-12-12-quick-maps-r/unnamed-chunk-2-1.png" title="plot of chunk unnamed-chunk-2" alt="plot of chunk unnamed-chunk-2" style="display: block; margin: auto;" />
Or, we can use the `maps` package and display a vector map of the U. S.


{% highlight r %}
us2 <- map("usa")
{% endhighlight %}

<img src="/socscistats/figure/source/2016-12-12-quick-maps-r/unnamed-chunk-3-1.png" title="plot of chunk unnamed-chunk-3" alt="plot of chunk unnamed-chunk-3" style="display: block; margin: auto;" />

{% highlight r %}
us2.df <- fortify(us2)
ggplot(data = us2.df, aes(x = long, y = lat)) + geom_polygon() 
{% endhighlight %}

<img src="/socscistats/figure/source/2016-12-12-quick-maps-r/unnamed-chunk-3-2.png" title="plot of chunk unnamed-chunk-3" alt="plot of chunk unnamed-chunk-3" style="display: block; margin: auto;" />
