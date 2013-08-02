---
layout: post
title: "OpenCPU 0.8 release!"
category: posts
cover: "http://images2.wikia.nocookie.net/__cb20120316224125/memoryalpha/en/images/6/6b/Earth_Spacedock,_2293.jpg"
---

Almost 2 years after the initial beta versions, we release the first official version of the OpenCPU framework. 
Based on experiences with the beta versions and new recent developments, OpenCPU version 0.8 has been rewritten from scratch.

# New in this release

This release comes with many completely new features

- OpenCPU can be used either locally with the `opencpu` package, or in the cloud.
- Native support for compiling documents using knitr, brew or pandoc.
- Revised API and new Javascript library to build OpenCPU Apps.
- Direct access in the cloud to R packages on CRAN and Github.
- Execute R scripts or knitr/sweave scripts, straight from Gist.
- Advanced security policies in the cloud server build on RAppArmor.

## Kick the tires

The latest release of OpenCPU is available form github:

{% highlight r %}
library(devtools)
install_github("opencpu", "jeroenooms")
library(opencpu)
{% endhighlight %}
    
That's it! You can now use the OpenCPU API. 

### OpenCPU Apps

We are working on a Javascript library [opencpu.js](http://github.com/jeroenooms/opencpu.js) which makes it easy to build R web applications
using OpenCPU. The repository of OpenCPU apps is simply the [opencpu github organization](http://github.com/opencpu). 
After installing the `opencpu` package, you can try to install some of the example apps. 

For example the nabel application plots live data from the Swiss National Air Pollution Monitoring Network:   

{% highlight r linenos=table %}
#install app: http://github.com/opencpu/nabel
install_github("nabel", "opencpu")
opencpu$browse("library/nabel/www")
{% endhighlight %}    
    
This will popup your browser and send you to the app url. You can also use OpenCPU to look at the source code or documentation for this app:

{% highlight r %}
#Source code for 'nabel' function
opencpu$browse("library/nabel/R/nabel")

#manuals in various formats
opencpu$browse("library/nabel/man/nabel/text")
opencpu$browse("library/nabel/man/nabel/html")
{% endhighlight %}
    
Try some of the other apps as well!

{% highlight r %}
#yahoo finance app
install_github("stocks", "opencpu")
opencpu$browse("library/stocks/www")

#plot stats for github users
install_github("gitstats", "opencpu")
opencpu$browse("library/gitstats/www")
{% endhighlight %}
      
#### Much more to come

Over the upcoming weeks we will post more on this blog, on how to run apps in the cloud, share reproducible documents, and much more.


    


