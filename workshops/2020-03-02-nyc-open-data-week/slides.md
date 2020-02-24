## NYC Open Data Week
## Socrata OpenData APIs
![Socrata](img/snu-geek.png)
### Ori Pleban
### Data Integration Architect
### ori.pleban@tylertech.com

===

<h1>What the heck<br />is Socrata?</h1>
![Socrata](img/White_orange_logo.png)

---

<img class="fullscreen-img" src="/presentations/img/at_table.jpg" />

<h2>Socrata is <span class="toy-store-blue">software</span> to make data <span class="blushing-salmon">more useful</span> to <span class="golden">more people</span>.</h2>

<!-- https://www.flickr.com/photos/hyku/2497370097 -->
---

<img class="fullscreen-img" src="/presentations/img/city.jpg" />

<h2><span class="toy-store-blue">Greater access</span> to <span class="blushing-salmon"> data</span> makes this universe <span class="golden">a better places to live</span></h2>

---

<img class="fullscreen-img" src="/presentations/img/city_hall.jpg" />

<h2>The Socrata platform is purpose-built for governement and makes it <span class="toy-store-blue">easy</span> for <span class="blushing-salmon">organizations</span> to share their public data with <span class="golden">developers</span></h2>


===

# So what is an API anyway?

![APIs](../../img/Bubble_blue.tif.png)

---

<div style="text-align: left; font-size: 3em; line-height: 1.1em">
  <span class="blushing-salmon">A</span>pplication<br/>
  <span class="fragment" data-fragment-index=0><span class="toy-store-blue">P</span>rogramming<br/></span>
  <span class="fragment" data-fragment-index=1><span class="golden">I</span>nterface</span>
</div>

---

# Common Language

A <span class="blushing-salmon">consistent</span> way for <span class="toy-store-blue">two software systems</span> to <span class="golden">communicate</span>.

---

# Stable Platform

A <span class="blushing-salmon">guarantee</span> that the <span class="toy-store-blue">language</span> will not <span class="golden">change</span> without notice.

---

# Contract

An API is a <span class="blushing-salmon">contract</span> between a <span class="toy-store-blue">provider</span> and a <span class="golden">consumer</span>.

===

# Why are APIs important?

![APIs](../../img/Gear.png)

---

## Open data is messy

<pre>
datavar 0 colorb_v
datavar 1 lum
datavar 2 absmag
datavar 3 appmag
datavar 4 texnum
datavar 5 distly
datavar 6 dcalc
datavar 7 plx
datavar 8 plxerr
datavar 9 vx
datavar 10 vy
datavar 11 vz
datavar 12 speed
datavar 13 hipnum
texturevar 4
texture -M 1 halo.sgi
    0.0000     0.0000     0.0000     0.650      0.89130      4.85    -26.72     1       0.00    0      0.000      0.00      0.000      0.000      0.000      0.000       0 # Sun
  -18.1007   143.5620  -242.6120     0.396     14.19036      1.85      9.10     1     920.90    1      3.540     39.27      0.000      0.000      0.000      0.000       1 # HIP1 HD224700 Gli
    5.0098     9.8817   -44.2976     1.038      0.31704      5.97      9.27     1     148.86    1     21.900     14.16      0.000      0.000      0.000      0.000       2 # HIP2 HD224690 Gli
 -123.2580   303.6977  -138.6362    -0.005    223.14508     -1.15      6.61     1    1160.14    1      2.810     22.42      0.000      0.000      0.000      0.000       3 # HIP3 HD224699 Gli
  -50.4801   149.0259  -112.4977     1.822      6.96657      2.62      9.05     1     630.56    1      5.170     37.72     -6.247    -32.276      9.713     34.280       8 # HIP8 HD224709 Gli
</pre>

from research.amnh.org

---

## A downloaded dataset is a stale dataset

![Clock](../../img/Alarm_clock.tif.png)

---

## Developers don’t want to manage custom datastores

![Hockey Puck](../../img/Database.tif.png)

---

## You want apps to be easily portable

![Rocket](../../img/Rocket.tif.png)

===

# The Socrata Open Data APIs

![SODA](../../img/can.png)

---

## Finding Data
<br />
### [opendata.cityofnewyork.us](https://opendata.cityofnewyork.us/)
<br />
### [www.opendatanetwork.com](https://www.opendatanetwork.com/)

---

### In the Data Catalog

![API Sidebar](img/pa.png)

---

## API Endpoints

<br />
<code style='font-size:120%;'>https://<span class="greenery">$domain</span>/resource/<span class="golden">$identifier</span>.<span class="blushing-salmon">$ext</span></code>

<br />

<p style='text-align: left; margin-left:50px;'><em>Where:</em></p>

- <code><span class="greenery">$domain</span></code> is the publisher's domain (ex: <code>data.pa.gov</code>)
- <code><span class="golden">$identifier</span></code> is a dataset's unique ID (ex: <code>ug4h-nsj9</code>)
- <code><span class="blushing-salmon">$ext</span></code> is <code>json</code>, <code>csv</code>, <code>xml</code>, or <code>rdf</code>


---

## Example: NYC Film Permits

<a target='blank' style='color:#FFF !important' href='https://data.cityofnewyork.us/resource/tg4x-b46p.json'><code style=''>https://<span class="greenery">data.cityofnewyork.us</span>/resource/<span class="golden">tg4x-b46p</span>.<span class="blushing-salmon">json</span></code></a>

<pre>
  <code data-trim contenteditable class="javascript">
[
  {
    "eventid": "519983",
    "eventtype": "Shooting Permit",
    "startdatetime": "2019-11-25T06:00:00.000",
    "enddatetime": "2019-11-25T10:00:00.000",
    "enteredon": "2019-11-22T15:13:39.000",
    "eventagency": "Mayor's Office of Film, Theatre & Broadcasting",
    "parkingheld": "WEST   48 STREET between 6 AVENUE and 7 AVENUE",
    "borough": "Manhattan",
    "communityboard_s": "5",
    "policeprecinct_s": "18",
    "category": "Television",
    "subcategoryname": "News",
    "country": "United States of America",
    "zipcode_s": "10036, 10105"
  },
  {
    "eventid": "519948",
    "eventtype": "Shooting Permit",
    "startdatetime": "2019-11-25T06:00:00.000",
    "enddatetime": "2019-11-25T20:30:00.000",
    "enteredon": "2019-11-22T13:55:42.000",
    "eventagency": "Mayor's Office of Film, Theatre & Broadcasting",
    "parkingheld": "EAST   71 STREET between MADISON AVENUE and PARK AVENUE",
    "borough": "Manhattan",
    "communityboard_s": "64, 8",
    "policeprecinct_s": "19, 22",
    "category": "Film",
    "subcategoryname": "Feature",
    "country": "United States of America",
    "zipcode_s": "10021, 10023"
  },
  {
    "eventid": "519941",
    "eventtype": "Shooting Permit",
    "startdatetime": "2019-11-25T07:00:00.000",
    "enddatetime": "2019-11-25T21:00:00.000",
    "enteredon": "2019-11-22T13:40:08.000",
    "eventagency": "Mayor's Office of Film, Theatre & Broadcasting",
    "parkingheld": "BROADWAY between WEST   75 STREET and WEST   78 STREET,  BROADWAY between WEST   75 STREET and WEST   78 STREET,  5 AVENUE between EAST   79 STREET and EAST   80 STREET",
    "borough": "Manhattan",
    "communityboard_s": "64, 7, 8",
    "policeprecinct_s": "19, 20, 22",
    "category": "Film",
    "subcategoryname": "Feature",
    "country": "United States of America",
    "zipcode_s": "10023, 10024, 10075"
  },
  {
    "eventid": "519916",
    "eventtype": "Shooting Permit",
    "startdatetime": "2019-11-25T06:00:00.000",
    "enddatetime": "2019-11-25T22:00:00.000",
    "enteredon": "2019-11-22T12:41:05.000",
    "eventagency": "Mayor's Office of Film, Theatre & Broadcasting",
    "parkingheld": "ATLANTIC AVENUE between COURT STREET and HENRY STREET,  COURT STREET between MONTAGUE STREET and JORALEMON STREET,  WASHINGTON PARK between MYRTLE AVENUE and DEKALB AVENUE,  DEKALB AVENUE between ASHLAND PLACE and WASHINGTON PARK,  ADELPHI STREET between GREENE AVENUE and LAFAYETTE AVENUE,  LAFAYETTE AVENUE between CARLTON AVENUE and CUMBERLAND STREET,  LAFAYETTE AVENUE between CARLTON AVENUE and ADELPHI STREET",
    "borough": "Brooklyn",
    "communityboard_s": "2, 6",
    "policeprecinct_s": "76, 84, 88",
    "category": "Television",
    "subcategoryname": "Episodic series",
    "country": "United States of America",
    "zipcode_s": "11201, 11205, 11217, 11238"
  },
  {
    "eventid": "519904",
    "eventtype": "Shooting Permit",
    "startdatetime": "2019-11-23T06:00:00.000",
    "enddatetime": "2019-11-23T20:00:00.000",
    "enteredon": "2019-11-22T11:57:36.000",
    "eventagency": "Mayor's Office of Film, Theatre & Broadcasting",
    "parkingheld": "BARROW STREET between BEDFORD STREET and 7 AVENUE SOUTH,  7 AVENUE SOUTH between BARROW STREET and COMMERCE STREET",
    "borough": "Manhattan",
    "communityboard_s": "2",
    "policeprecinct_s": "6",
    "category": "Film",
    "subcategoryname": "Feature",
    "country": "United States of America",
    "zipcode_s": "10014"
  },... and so on
]
  </code>
</pre>

---

## Simple Filters

<a target='blank' style='color:#FFF !important' href='https://data.cityofnewyork.us/resource/tg4x-b46p.json?category=Television'><code style=''>https://<span class="greenery">data.cityofnewyork.us</span>/resource/<span class="golden">tg4x-b46p</span>.<span class="blushing-salmon">json</span>
<br />?<span class="toy-store-blue">category</span>=<span style="color:MediumOrchid">Television</span></code></a>

<pre><code data-trim contenteditable class="javascript">
[
  {
    "eventid": "519636",
    "eventtype": "Shooting Permit",
    "startdatetime": "2019-11-25T09:00:00.000",
    "enddatetime": "2019-11-26T00:00:00.000",
    "enteredon": "2019-11-21T11:20:51.000",
    "eventagency": "Mayor's Office of Film, Theatre & Broadcasting",
    "parkingheld": "34 AVENUE between 36 STREET and 35 STREET,  35 STREET between 34 AVENUE and 35 AVENUE,  35 STREET between ASTORIA BOULEVARD and 28 AVENUE,  28 AVENUE between 35 STREET and 34 STREET,  35 STREET between 28 AVENUE and 30 AVENUE,  28 AVENUE between 33 STREET and 34 STREET",
    "borough": "Queens",
    "communityboard_s": "1",
    "policeprecinct_s": "114",
    "category": "Television",
    "subcategoryname": "Cable-episodic",
    "country": "United States of America",
    "zipcode_s": "11103, 11106"
  },
  {
    "eventid": "516485",
    "eventtype": "Shooting Permit",
    "startdatetime": "2019-11-25T07:00:00.000",
    "enddatetime": "2019-11-25T23:00:00.000",
    "enteredon": "2019-11-12T17:12:27.000",
    "eventagency": "Mayor's Office of Film, Theatre & Broadcasting",
    "parkingheld": "MOSHOLU AVENUE between WEST  256 STREET and WEST  254 STREET,  RIVERDALE AVENUE between WEST  256 STREET and WEST  258 STREET,  RIVERDALE AVENUE between WEST  258 STREET and WEST  260 STREET",
    "borough": "Bronx",
    "communityboard_s": "8",
    "policeprecinct_s": "50",
    "category": "Television",
    "subcategoryname": "Episodic series",
    "country": "United States of America",
    "zipcode_s": "10471"
  },
  {
    "eventid": "519527",
    "eventtype": "Shooting Permit",
    "startdatetime": "2019-11-25T06:00:00.000",
    "enddatetime": "2019-11-26T00:00:00.000",
    "enteredon": "2019-11-20T16:43:16.000",
    "eventagency": "Mayor's Office of Film, Theatre & Broadcasting",
    "parkingheld": "PARK AVENUE SOUTH between EAST   21 STREET and EAST   18 STREET,  EAST   20 STREET between PARK AVENUE SOUTH and 3 AVENUE,  EAST   19 STREET between PARK AVENUE SOUTH and 3 AVENUE,  IRVING PLACE between EAST   20 STREET and EAST   17 STREET",
    "borough": "Manhattan",
    "communityboard_s": "5, 6",
    "policeprecinct_s": "13",
    "category": "Television",
    "subcategoryname": "Episodic series",
    "country": "United States of America",
    "zipcode_s": "10003, 10010"
  },
  {
    "eventid": "519453",
    "eventtype": "Shooting Permit",
    "startdatetime": "2019-11-25T06:00:00.000",
    "enddatetime": "2019-11-25T22:00:00.000",
    "enteredon": "2019-11-20T14:34:41.000",
    "eventagency": "Mayor's Office of Film, Theatre & Broadcasting",
    "parkingheld": "PARK AVENUE between EAST   70 STREET and EAST   71 STREET,  PARK AVENUE between EAST   70 STREET and EAST   69 STREET,  EAST   69 STREET between PARK AVENUE and MADISON AVENUE,  PARK AVENUE between EAST   69 STREET and EAST   68 STREET,  PARK AVENUE between EAST   68 STREET and EAST   67 STREET,  EAST   68 STREET between PARK AVENUE and MADISON AVENUE,  MADISON AVENUE between EAST   67 STREET and EAST   68 STREET,  MADISON AVENUE between EAST   68 STREET and EAST   69 STREET,  MADISON AVENUE between EAST   69 STREET and EAST   70 STREET,  37 STREET between 43 AVENUE and SKILLMAN AVENUE,  38 STREET between 43 AVENUE and SKILLMAN AVENUE,  43 AVENUE between 39 STREET and 37 STREET,  37 STREET between QUEENS BOULEVARD and 43 AVENUE,  QUEENS BOULEVARD between 37 STREET and 38 STREET",
    "borough": "Manhattan",
    "communityboard_s": "2, 8",
    "policeprecinct_s": "108, 19",
    "category": "Television",
    "subcategoryname": "Episodic series",
    "country": "United States of America",
    "zipcode_s": "10021, 10065, 11101"
  }, ... // and so on
]
</code></pre>

---

## SoQL Queries
// https://data.cityofnewyork.us/resource/tg4x-b46p.json?$WHERE=data_trunc_y(startdatetime) >= '2019-01-01' AND borough = "Queens"
<a href="https://data.cityofnewyork.us/resource/tg4x-b46p.json?$select=eventid,category, subcategoryname,borough&$where=startdatetime >='2019-01-01' AND borough ='Queens'"><code>https://data.cityofnewyork.us/resource/tg4x-b46p.json?<span class="toy-store-blue">$WHERE</span>=<span class="golden">startdatetime &gte; '2019-01-01' AND borough ='Queens'</span></code></a>

<pre><code data-trim contenteditable class="javascript">
  [
    {
      "eventid": "496377",
      "category": "Television",
      "subcategoryname": "Episodic series",
      "borough": "Queens"
    },
    {
      "eventid": "496675",
      "category": "Television",
      "subcategoryname": "Episodic series",
      "borough": "Queens"
    },
    {
      "eventid": "497090",
      "category": "Television",
      "subcategoryname": "Cable-other",
      "borough": "Queens"
    },
    {
      "eventid": "498138",
      "category": "Film",
      "subcategoryname": "Feature",
      "borough": "Queens"
    },
    {
      "eventid": "505645",
      "category": "Television",
      "subcategoryname": "Episodic series",
      "borough": "Queens"
    },
    {
      "eventid": "507446",
      "category": "Television",
      "subcategoryname": "Episodic series",
      "borough": "Queens"
    },..., and so on
  ]
</code></pre>
<small style="padding-top: 5em">For more details see <a href="http://dev.socrata.com">dev.socrata.com</a></small>

---

## SoQL Clauses

<table class="table table-striped table-hover">
  <thead>
    <tr>
      <th>Parameter</th>
      <th>Description</th>
      <th>Default</th>
      <th>In <code class="highlighter-rouge">$query</code></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td><a href="/docs/queries/select.html"><code class="highlighter-rouge">$select</code></a></td>
      <td>The set of columns to be returned, similar to a <code class="highlighter-rouge">SELECT</code> in SQL</td>
      <td>All columns, equivalent to <code class="highlighter-rouge">$select=*</code></td>
      <td><code class="highlighter-rouge">SELECT</code></td>
    </tr>
    <tr>
      <td><a href="/docs/queries/where.html"><code class="highlighter-rouge">$where</code></a></td>
      <td>Filters the rows to be returned, similar to <code class="highlighter-rouge">WHERE</code></td>
      <td>No filter</td>
      <td><code class="highlighter-rouge">WHERE</code></td>
    </tr>
    <tr>
      <td><a href="/docs/queries/order.html"><code class="highlighter-rouge">$order</code></a></td>
      <td>Column to order results on, similar to ORDER BY in SQL</td>
      <td>Unspecified order</td>
      <td><code class="highlighter-rouge">ORDER BY</code></td>
    </tr>
    <tr>
      <td><a href="/docs/queries/group.html"><code class="highlighter-rouge">$group</code></a></td>
      <td>Column to group results on, similar to GROUP BY in SQL</td>
      <td>No grouping</td>
      <td><code class="highlighter-rouge">GROUP BY</code></td>
    </tr>
    <tr>
      <td><a href="/docs/queries/having.html"><code class="highlighter-rouge">$having</code></a></td>
      <td>Filters the rows that result from an aggregation, similar to <code class="highlighter-rouge">HAVING</code></td>
      <td>No filter</td>
      <td><code class="highlighter-rouge">HAVING</code></td>
    </tr>
    <tr>
      <td><a href="/docs/queries/limit.html"><code class="highlighter-rouge">$limit</code></a></td>
      <td>Maximum number of results to return</td>
      <td>1000 (2.0 endpoints: maximum of 50,000; 2.1: unlimited <a href="/docs/endpoints.html">»</a>)</td>
      <td><code class="highlighter-rouge">LIMIT</code></td>
    </tr>
    <tr>
      <td><a href="/docs/queries/offset.html"><code class="highlighter-rouge">$offset</code></a></td>
      <td>Offset count into the results to start at, used for paging</td>
      <td>0</td>
      <td><code class="highlighter-rouge">OFFSET</code></td>
    </tr>
    <tr>
      <td><a href="/docs/queries/q.html"><code class="highlighter-rouge">$q</code></a></td>
      <td>Performs a full text search for a value.</td>
      <td>No search</td>
      <td><code class="highlighter-rouge">N/A</code></td>
    </tr>
    <tr>
      <td><a href="/docs/queries/query.html"><code class="highlighter-rouge">$query</code></a></td>
      <td>A full SoQL query string, all as one parameter</td>
      <td>N/A</td>
      <td><code class="highlighter-rouge">N/A</code></td>
    </tr>
  </tbody>
</table>

---

## Aggregating Data

<a href="https://data.cityofnewyork.us/resource/tg4x-b46p.json?$select=borough, count(*) as number_of_permits&$group=borough&$where=startdatetime >='2019-01-01'">
  <code>https://data.cityofnewyork.us/resource/tg4x-b46p.json?
    <span class="toy-store-blue">$SELECT</span>=
    <span class="golden">borough, count(*) as number_of_permits</span>
    <span class="toy-store-blue">$WHERE</span>=
    <span class="golden">startdatetime &gte; '2019-01-01'</span>
  </code>
</a>

<pre><code data-trim contenteditable class="javascript">
  [
    {
      "borough": "Brooklyn",
      "number_of_permits": "2365"
    },
      {
      "borough": "Manhattan",
      "number_of_permits": "3586"
    },
    {
      "borough": "Queens",
      "number_of_permits": "1336"
    },
    {
      "borough": "Bronx",
      "number_of_permits": "246"
    },
    {
      "borough": "Staten Island",
      "number_of_permits": "170"
    }
  ]
</code></pre>

---

## Geospatial Queries
  <a target='blank' style='color:#FFF !important' href='https://data.pa.gov/resource/fnrp-gye7.json?$where=within_circle(location_1,40.2642873,-76.8861474,1000)'><code style=''>https://<span class="greenery">data.pa.gov</span>/resource/<span class="golden">fnrp-gye7</span>.<span class="blushing-salmon">json</span>
  <br />?<span class="toy-store-blue">$where=</span><span style="color:MediumOrchid">within_circle(location_1,40.2642873,-76.8861474,1000)</span></code></a>

  <pre><code data-trim contenteditable class="javascript">
  [
    {
      "county_description": "DAUPHIN (6)",
      "county_key": "22",
      "court_disposition": "Guilty",
      "determination_year": "2015",
      "dog_info_age": "3 years",
      "dog_info_breed": "American Bulldog",
      "dog_info_predator": "Dog",
      "file_date": "2015-10-16T00:00:00.000",
      "hearing_date": "2015-11-23T00:00:00.000",
      "location_1": {
      "type": "Point",
      "coordinates": [
        -76.890435,
        40.270365
      ]
    },
      "location_1_address": "268 Calder St",
      "location_1_city": "Harrisburg",
      "location_1_state": "PA",
      "location_1_zip": "17102",
      "owner_address": "268 Calder St",
      "owner_city": "Harrisburg",
      "owner_county": "DAUPHIN (6)",
      "owner_first_name": "Tyson",
      "owner_last_name": "Stokes",
      "owner_state": "PA",
      "owner_zip": "17102",
      "status_description": "City Limits"
    }
  ]
  </code></pre>

---
## Paging Through Data

<a target='_blank' style='color:#FFF !important' href='https://data.pa.gov/resource/fnrp-gye7.json?$limit=50&$offset=100'><code style=''>https://<span class="greenery">data.pa.gov</span>/resource/<span class="golden">fnrp-gye7</span>.<span class="blushing-salmon">json</span>
<br />?<span class="toy-store-blue">$limit</span>=<span style="color:MediumOrchid">50</span>&<span class="toy-store-blue">$offset</span>=<span style="color:MediumOrchid">100</span></code></a>

---

## SoQL Function Listing

<a target='_blank' style='color:#FFF !important' href='https://dev.socrata.com/docs/functions/'>

---

## Application Tokens

1. Register at [https://data.pa.gov/profile/app_tokens](https://data.pa.gov/profile/app_tokens)
2. Include as:
  - <code><span class="toy-store-blue">X-App-Token</span>: <span class="golden">$token</span></code> HTTP Header or ...
  - The <code><span class="toy-store-blue">$$app_token</span>=<span class="golden">$token</span></code> URL parameter
3. Profit!!! (from more API requests)

===

# Help!

---

## Developer Portal

# [dev.socrata.com](http://dev.socrata.com)

<div class="footnote">Community powered! Learn how to <a href="http://dev.socrata.com/contributing.html">contribute</a>.</div>

---

## Getting Help

![Getting Help](/presentations/img/live-support.gif)
- Stack Overflow: [soda](http://stackoverflow.com/questions/tagged/soda) or [socrata](http://stackoverflow.com/questions/tagged/socrata)

---

## Libraries &amp; SDKs

<img src="../../img/socrata-heart-opensource.png"/>

### [dev.socrata.com/libraries/](http://dev.socrata.com/libraries/)

<div class="footnote"><a href="http://socrata.github.io/soda-ruby/">Ruby</a>, <a href="https://github.com/socrata/soda-scala">Scala</a>, <a href="http://socrata.github.io/soda-java/">Java</a>, <a href="https://github.com/socrata/soda-ios-sdk">ObjectiveC</a>, <a href="https://github.com/Chicago/RSocrata">R</a>, <a href="https://github.com/socrata/soda-swift">Swift</a>, etc.</div>

===


<img class="fullscreen-img" src="/presentations/img/maggie.jpg"/>

# Thanks!
