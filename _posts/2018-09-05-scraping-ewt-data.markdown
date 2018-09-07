---
layout: post
title:  "Scraping Emergency Room Wait Times"
date:   2018-09-05 14:16:59 -0600
categories: data-science
math: true
---

I noticed that Alberta Health Services posts the wait times for emergency departments across the province. Out of curiosity I wondered if I could find some trends and possibly even predict wait times for a given time of day or week.

So I've set up an AWS Lambda script to periodically scrape the times from the site and save them to a DynamoDB table. 

The wait times script is [here][ewt-script-url].

I also set up a script to connect to a weather api and save weather details to another DynamoDB table. Might be interesting to see if there are interactions between weather and wait times. 

The weather script is [here][weather-script-url]

Once these gather enough data, I'll throw some analysis at it.


[ewt-script-url]: https://github.com/srveale/aws-ewt
[weather-script-url]: https://github.com/srveale/aws-weather
