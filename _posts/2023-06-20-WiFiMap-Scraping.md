---
title: WiFiMap Scraping or How I Built My Own Offline WiFi Database
layout: post
---

# How I scraped WifiMap database for offline access
I wanted to have an offline database of public WiFi hotspots, but collecting the data myself was too difficult. So I decided to scrape it from existing sources. I found several websites that offer this kind of information, such as [3wifi](http://3wifi.stascorp.com), [WiFiMap](https://www.wifimap.io), and more.
## My initial attempts
At first, I thought of downloading a [cracked WiFi Map](https://4pda.to/forum/index.php?showtopic=609030&st=300#entry68027404) android app and extracting the cached data. However, this turned out to be impractical. The data was stored somewhere obscure and I could only use the offline map feature. I needed a way to inspect the traffic and extract the data.
## A better approach
I decided to use a combination of WiFi Map and [HttpCanary](https://4pda.to/forum/index.php?s=&showtopic=957572&view=findpost&p=99306859). I was able to capture [useful data](https://gist.github.com/nekotov/fd2d8682541034e5e01f413f3a897ff4#file-dump-hcy) from the app, but it was outdated.
## The breakthrough
After analyzing the packets more closely, I discovered [JSON responses](https://gist.github.com/nekotov/fd2d8682541034e5e01f413f3a897ff4#file-realtime-json) that contained real-time information about nearby WiFi hotspots with passwords. These packets were triggered by swiping on the map. This was exactly what I needed.
## The automation
To automate the scraping process, I used:
 - ADB - for simulating map scrolling
 - HttpCanary with "Upload to Server" plugin - for collecting packets
 - Python3 - for cleaning and processing the raw data

## The results
 - I collected several thousand points and converted them to map points (.kml)
 - I learned new things about scraping and automation
 - I made all of my collected data available for free on [Github](https://github.com/nekotov/LibriFI)

## The next steps
 1. [ ] Automate the collection and publishing of data
 2. [ ] Improve the speed and quality of scraping and data

