---
title: Scraping or Extracting from coingecko rest api using python
date: 2019-06-20 21:34:00 Z
categories:
- scripts
tags:
- python
- rest api
- fiverr
---

I needed all the symbols and their high and low 24 hour values,in us dollars

    import json
    import urllib.request
    
    
    url = 'https://api.coingecko.com/api/v3/coins/markets?vs_currency=usd&order=market_cap_desc&per_page=100&page=1&sparkline=false'
    req = urllib.request.Request(url)
    
    ##parsing response
    myfile=open("coingecko.csv","w",encoding="utf8")
    headers="Symbol,High 24h,Low 24h\n"
    myfile.write(headers)
    
    r = urllib.request.urlopen(req).read()
    cont = json.loads(r.decode('utf-8'))
    for market in cont:
        symbol=(market["symbol"])
        high=(market["high_24h"])
        low=(market["low_24h"])
        content=symbol+","+str(high)+","+str(low)+"\n"
        myfile.write(content)
    print("job complete")

**[Still Struggling ? Get help with this on fiverr now](https://www.fiverr.com/muazzammullah/scrape-extract-rest-api-data-with-python)**