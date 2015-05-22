---
layout: post
title: Web scraper without IP limit problem!
date: 2015-03-01 22:00:00
---

As data scientists and researchers, most of the time we crawl our own data from various sources. Sometimes we also use online services to query and collect results. Such services have limits by IP most of the time.

Using tools that we are already familiar with, we can also solve IP limit problem. In this blog post, I will describe an example solution that I have been using. I will use Python to write my script and import some very useful packages that I need for this task.

In this example scenario, I need to use an online service called www.useful-service.com. My task is to submit an url to webform in this page and collect results from redirected webpage. In this particular example webpage content is produced asynchronously and [requests](https://pypi.python.org/pypi/requests) or [urllib](https://docs.python.org/2/library/urllib.html) packages can only gather webpage content onload, without any dynamically loaded content. When scripts need to wait page content to load, [selenium package](https://pypi.python.org/pypi/selenium) is a perfect choice. It opens a browser instance and give access to control elements in the page content. I also find [beautifulsoup](https://pypi.python.org/pypi/beautifulsoup4/4.3.2) very useful when I parse and play with webpage content.

The main difficult and the motivation to write this blogpost is to explain how to get away with IP limitation. For this purposes I decided to use Tor network to make my requests from different IP addresses.

In the [Tor browsers](https://www.torproject.org/download/download) network preferences, I set network settings to use manual proxy and changes port address as shown in figure below.

<div style="text-align:center;"><img src="{{ site.baseurl }}/images/tor_settings.png"></div>

This setting allow me to connect Tor network using port 9150 and every request will send through different IP address. Later I will use these port to create selenium webdriver and connect webpage on this port.

```python
import os, sys
import subprocess, signal
import time

from bs4 import BeautifulSoup
import selenium as sl
from selenium.webdriver import Firefox, FirefoxProfile

profile = FirefoxProfile()
profile.set_preference('network.proxy.type', 1)
profile.set_preference('network.proxy.socks', '127.0.0.1')
profile.set_preference('network.proxy.socks_port', 9150)
driver = Firefox(profile)

def webpage_connect(baseUrl, pageUrl):
    print 'Connecting...'
    driver.get(URL)

    driver.find_element_by_id("url_box").send_keys(pageUrl)
    submitButton = driver.find_element_by_id('url_submit')
    submitButton.click() # Submits a request for pageUrl

    print pageUrl
    trial = 0
    toParse = False
    while trial < 100:
        print 'Trying ...', trial
        html = driver.page_source
        if 'search-result-item-details' in html:
            toParse = True
            break

        if "URL could not be reached" in html:
            print 'Cant reached'
            return ['url_unreacable']

        time.sleep(1)
        trial += 1

    if trial >= 100:
        return ['timeout']

    sources = list()
    if toParse:
        print 'parsing'
        soup = BeautifulSoup(html)
        for resultBox in soup.find_all('div', class_='search-result-item-details'):
            res = resultBox.span.text.strip()
            print res
            sources.append(res)

    return sources

if __name__ == '__main__':
    serviceUrl = 'https://www.useful-service.com/'
    testurl = 'https://www.some-other-page.com/index.html?id=123'
    webpage_connect(serviceUrl, testurl)
```

Code piece shown above is to create Firefox driver to collect data. I changed settings to be able to use Tor port to collect data without any IP problem.
