ForexCurrencyCorrelations
=========================
Application computes matrix of correlations between currencies and displays them as [Minimum Spanning Tree](http://en.wikipedia.org/wiki/Minimum_spanning_tree).
Graphs are constructed based on real data that come from NY Forex. At this moment, the most popular 35 Forex currencies are used to construct graphs and [base currency](http://en.wikipedia.org/wiki/Currency_pair#Base_currency) is Polish Zloty  (PLN). 

It is available on OpenShift cloud, and you can take a look here:
http://front-comparator.rhcloud.com/

Application consists of three independent microservices, communicating via REST with each other:
- front (http://front-comparator.rhcloud.com/): simply UI
- cc (http://cc-comparator.rhcloud.com/): polls data from Yahoo Finance for further usage and caches it into MongoDB
- mst (http://mst-comparator.rhcloud.com/): based on given input (time series), constructs graphs

Used technologies:
- Server side is written in Java EE7 running on Wildfly 8 (hosted OpenShift cloud)
- Front end: HTML5 + JS + Bootstrap + Angular JS


Give it a shot:
http://front-comparator.rhcloud.com/
