Description
=========================
ForexCurrencyCorrelations computes correlations between currencies and displays them as [Minimum Spanning Tree](http://en.wikipedia.org/wiki/Minimum_spanning_tree).
Graphs are constructed based on real data that come from NY Forex. At this moment, the most popular 35 Forex currencies are used to build graphs and Polish Zloty (PLN) is [base currency](http://en.wikipedia.org/wiki/Currency_pair#Base_currency). 

Cloud
--------------
Application is hosted on OpenShift cloud:
http://front-comparator.rhcloud.com/

Components
--------------
ForexCurrencyCorrelations consists of two independent microservices (cc + mst) and third that is responsible for handling user iteractions (front). Each of them communicates via REST with others:
- front (http://front-comparator.rhcloud.com/): simply UI
- cc (http://cc-comparator.rhcloud.com/): polls data from Yahoo Finance for further usage and caches it into MongoDB + creates time series
- mst (http://mst-comparator.rhcloud.com/): based on given input (time series), constructs graphs

Used technologies
--------------
- Server side is written in Java EE7 running on Wildfly 8 (hosted in OpenShift cloud)
- Front end: HTML5 + JS + Bootstrap + Angular JS

Browse my repo (cc, mst or front) if you're looking for source code.
