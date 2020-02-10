## Code4PA Hackathon
## Socrata OpenData APIs
![Socrata](img/snu-geek.png)
### Ori Pleban
### Web Developer & Student
### ori@pleban.org

===

<h1>Who the heck<br />are you?</h1>
![Socrata](img/White_orange_logo.png)

---

<img class="fullscreen-img" src="/presentations/img/at_table.jpg" />

<h2>We build <span class="toy-store-blue">software</span> to make data <span class="blushing-salmon">more useful</span> to <span class="golden">more people</span>.</h2>

<!-- https://www.flickr.com/photos/hyku/2497370097 -->
---

<img class="fullscreen-img" src="/presentations/img/city.jpg" />

<h2>We believe that <span class="toy-store-blue">greater access</span> to <span class="blushing-salmon"> data</span> makes this universe <span class="golden">a better places to live</span></h2>

---

<img class="fullscreen-img" src="/presentations/img/city_hall.jpg" />

<h2>We make it <span class="toy-store-blue">easy</span> for <span class="blushing-salmon">organizations</span> to share their public data with <span class="golden">developers</span></h2>


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
### [data.pa.gov](https://data.pa.gov/)
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

## Example: Dangerous Dogs Data Set

<a target='blank' style='color:#FFF !important' href='https://data.pa.gov/resource/fnrp-gye7.json'><code style=''>https://<span class="greenery">data.pa.gov</span>/resource/<span class="golden">fnrp-gye7</span>.<span class="blushing-salmon">json</span></code></a>

<pre>
  <code data-trim contenteditable class="javascript">
[
  {
    "county_description": "BUCKS (7)",
    "county_key": "9",
    "court_disposition": "Guilty",
    "determination_year": "2002",
    "dog_info_age": "2 YRS.",
    "dog_info_breed": "MIXED BREED",
    "dog_info_predator": "Dog",
    "file_date": "2002-12-12T00:00:00.000",
    "hearing_date": "2003-02-28T00:00:00.000",
    "location_1_address": "PO BOX 432",
    "location_1_city": "REVERE",
    "location_1_state": "PA",
    "location_1_zip": "18953",
    "owner_address": "PO BOX 432",
    "owner_city": "REVERE",
    "owner_county": "BUCKS (7)",
    "owner_first_name": "DAVID",
    "owner_last_name": "GERSENSON",
    "owner_state": "PA",
    "owner_zip": "18953",
    "status_description": "Closed"
  },
  {
    "county_description": "ALLEGHENY (4)",
    "county_key": "2",
    "court_disposition": "Guilty",
    "determination_year": "2003",
    "dog_info_age": "11 YRS.",
    "dog_info_breed": "MIXED BREED",
    "dog_info_predator": "Dog",
    "file_date": "2003-06-30T00:00:00.000",
    "hearing_date": "2003-06-30T00:00:00.000",
    "location_1_address": "2208 ORCHARD HILL ROAD",
    "location_1_city": "JEFFERSON HILLS",
    "location_1_state": "PA",
    "location_1_zip": "15025",
    "owner_address": "2208 ORCHARD HILL ROAD",
    "owner_city": "JEFFERSON HILLS",
    "owner_county": "ALLEGHENY (4)",
    "owner_first_name": "SHANEA",
    "owner_last_name": "NAKONECNY",
    "owner_state": "PA",
    "owner_zip": "15025",
    "status_description": "Deceased"
  },
  {
    "county_description": "BRADFORD (3)",
    "county_key": "8",
    "court_disposition": "Guilty",
    "determination_year": "2003",
    "dog_info_age": "7 YRS.",
    "dog_info_breed": "Rottweiler",
    "dog_info_predator": "Dog",
    "file_date": "2003-07-09T00:00:00.000",
    "hearing_date": "2003-07-09T00:00:00.000",
    "location_1_address": "RR 2, BOX 100",
    "location_1_city": "WYSOX",
    "location_1_state": "PA",
    "location_1_zip": "18854",
    "owner_address": "RR 2, BOX 100",
    "owner_city": "WYSOX",
    "owner_county": "BRADFORD (3)",
    "owner_first_name": "THERON",
    "owner_last_name": "WICKWIRE",
    "owner_state": "PA",
    "owner_zip": "18854",
    "status_description": "Deceased"
  },
  {
    "county_description": "WESTMORELAND (4)",
    "county_key": "65",
    "court_disposition": "Guilty",
    "determination_year": "2004",
    "dog_info_age": "ADULT",
    "dog_info_breed": "MIXED BREED",
    "dog_info_predator": "Dog",
    "file_date": "2004-06-10T00:00:00.000",
    "hearing_date": "2004-06-10T00:00:00.000",
    "location_1_address": "RT 982 HOUSE 520",
    "location_1_city": "NEW DERRY",
    "location_1_state": "PA",
    "location_1_zip": "15627",
    "owner_address": "RT 982 HOUSE 520",
    "owner_city": "NEW DERRY",
    "owner_county": "WESTMORELAND (4)",
    "owner_first_name": "VERONICA",
    "owner_last_name": "SIMMS",
    "owner_state": "PA",
    "owner_zip": "15627",
    "status_description": "Deceased"
  },
  {
    "county_description": "WYOMING (3)",
    "county_key": "66",
    "court_disposition": "Guilty",
    "determination_year": "2004",
    "dog_info_age": "9 YRS.",
    "dog_info_breed": "Labrador Retriever",
    "dog_info_predator": "Dog",
    "file_date": "2004-06-09T00:00:00.000",
    "hearing_date": "2004-06-03T00:00:00.000",
    "location_1_address": "RR 1, BOX 81",
    "location_1_city": "NOXEN",
    "location_1_state": "PA",
    "location_1_zip": "18636",
    "owner_address": "RR 1, BOX 81",
    "owner_city": "NOXEN",
    "owner_county": "WYOMING (3)",
    "owner_first_name": "KIMBERLY",
    "owner_last_name": "MERRYMAN",
    "owner_state": "PA",
    "owner_zip": "18636",
    "status_description": "Closed"
  },
  {
    "county_description": "WYOMING (3)",
    "county_key": "66",
    "court_disposition": "Guilty",
    "determination_year": "2004",
    "dog_info_age": "3 YRS.",
    "dog_info_breed": "MIXED BREED",
    "dog_info_predator": "Dog",
    "file_date": "2004-06-09T00:00:00.000",
    "hearing_date": "2004-06-03T00:00:00.000",
    "location_1_address": "RR 1, BOX 81",
    "location_1_city": "NEXON",
    "location_1_state": "PA",
    "location_1_zip": "18636",
    "owner_address": "RR 1, BOX 81",
    "owner_city": "NEXON",
    "owner_county": "WYOMING (3)",
    "owner_first_name": "KIMBERLY",
    "owner_last_name": "MERRYMAN",
    "owner_state": "PA",
    "owner_zip": "18636",
    "status_description": "Closed"
  }, ... // and so on
]
  </code>
</pre>

---

## Simple Filters

<a target='blank' style='color:#FFF !important' href='https://data.pa.gov/resource/phiq-bthj.json?merchant=DELAWARE DMV DOVER'><code style=''>https://<span class="greenery">data.pa.gov</span>/resource/<span class="golden">fnrp-gye7</span>.<span class="blushing-salmon">json</span>
<br />?<span class="toy-store-blue">dog_info_breed</span>=<span style="color:MediumOrchid">Chihuahua</span></code></a>

<pre><code data-trim contenteditable class="javascript">
[
  {
    "county_description": "DELAWARE (7)",
    "county_key": "23",
    "court_disposition": "Other",
    "determination_year": "1997",
    "dog_info_age": "4 YRS.",
    "dog_info_breed": "Chihuahua",
    "dog_info_predator": "Dog",
    "file_date": "1997-01-28T00:00:00.000",
    "location_1_address": "209 S. 4TH/2ND FLR.",
    "location_1_city": "COLWYN",
    "location_1_state": "PA",
    "location_1_zip": "19023",
    "owner_address": "209 S. 4TH/2ND FLR.",
    "owner_city": "COLWYN",
    "owner_county": "DELAWARE (7)",
    "owner_first_name": "CATRINA",
    "owner_last_name": "JORDEN",
    "owner_state": "PA",
    "owner_zip": "19023",
    "status_description": "Closed"
  },
  {
    "county_description": "LEBANON (6)",
    "county_key": "38",
    "court_disposition": "Other",
    "determination_year": "2000",
    "dog_info_age": "1 YR.",
    "dog_info_breed": "Chihuahua",
    "dog_info_predator": "Dog",
    "file_date": "2000-02-24T00:00:00.000",
    "location_1": {
      "type": "Point",
      "coordinates": [
        -76.429636,
        40.346751
      ]
  },
    "location_1_address": "1014 MIFFLIN STREET",
    "location_1_city": "LEBANON",
    "location_1_state": "PA",
    "location_1_zip": "17046",
    "owner_address": "1014 MIFFLIN STREET",
    "owner_city": "LEBANON",
    "owner_county": "LEBANON (6)",
    "owner_first_name": "FULVIO",
    "owner_last_name": "RANGEL",
    "owner_state": "PA",
    "owner_zip": "17046",
    "status_description": "Closed"
  },
  {
    "county_description": "DELAWARE (7)",
    "county_key": "23",
    "court_disposition": "Not Guilty",
    "determination_year": "1999",
    "dog_info_age": "NULL",
    "dog_info_breed": "Chihuahua",
    "dog_info_predator": "Dog",
    "file_date": "1998-12-18T00:00:00.000",
    "hearing_date": "1999-04-27T00:00:00.000",
    "location_1": {
    "type": "Point",
      "coordinates": [
        -75.383636,
        39.916002
      ]
    },
    "location_1_address": "312 E. BALTIMORE AVE",
    "location_1_city": "MEDIA",
    "location_1_state": "PA",
    "location_1_zip": "19063",
    "owner_address": "312 E. BALTIMORE AVE",
    "owner_city": "MEDIA",
    "owner_county": "DELAWARE (7)",
    "owner_first_name": "BETTY",
    "owner_last_name": "LEE",
    "owner_state": "PA",
    "owner_zip": "19063",
    "status_description": "Closed"
  },
  {
    "county_description": "FULTON (6)",
    "county_key": "29",
    "court_disposition": "Guilty",
    "determination_year": "2003",
    "dog_info_age": "14 MOS.",
    "dog_info_breed": "Chihuahua",
    "dog_info_predator": "Dog",
    "file_date": "2003-11-03T00:00:00.000",
    "hearing_date": "2003-11-03T00:00:00.000",
    "location_1": {
    "type": "Point",
      "coordinates": [
        -77.963112,
        40.062847
      ]
    },
    "location_1_address": "131 BROWN ROAD APT. 1",
    "location_1_city": "FORT LITTLETON",
    "location_1_state": "PA",
    "location_1_zip": "17223",
    "owner_address": "131 BROWN ROAD APT. 1",
    "owner_city": "FORT LITTLETON",
    "owner_county": "FULTON (6)",
    "owner_first_name": "KENNETH",
    "owner_last_name": "FOX",
    "owner_state": "PA",
    "owner_zip": "17223",
    "status_description": "Registered"
  }, ... // and so on
]
</code></pre>

---

## SoQL Queries

<a href="https://data.pa.gov/resource/fnrp-gye7.json?$SELECT=count_description,dog_info_breed,dog_info_age&$WHERE=court_disposition = 'Guilty' AND determination_year > 2016 AND dog_info_breed = 'Chihuahua"><code>https://data.pa.gov/resource/fnrp-gye7.json?<span class="toy-store-blue">$WHERE</span>=<span class="golden">court_disposition = 'Guilty' AND determination_year &gt; 2016 AND dog_info_breed = 'Chihuahua'</span></code></a>

<pre><code data-trim contenteditable class="javascript">
  [
    {
      "county_description": "MONROE (3)",
      "county_key": "45",
      "court_disposition": "Guilty",
      "determination_year": "2017",
      "dog_info_age": "1 year",
      "dog_info_breed": "Chihuahua",
      "dog_info_predator": "Dog",
      "file_date": "2017-02-13T00:00:00.000",
      "hearing_date": "2017-06-01T00:00:00.000",
      "location_1": {
      "type": "Point",
      "coordinates": [
      -75.183613,
      41.004163
      ]
      },
      "location_1_address": "202 N Courtland St",
      "location_1_city": "East Strousdsburg",
      "location_1_state": "PA",
      "location_1_zip": "18301",
      "owner_address": "202 N Courtland St",
      "owner_city": "East Strousdsburg",
      "owner_county": "MONROE (3)",
      "owner_first_name": "Karen",
      "owner_last_name": "Garris",
      "owner_state": "PA",
      "owner_zip": "18301",
      "status_description": "Open"
    }
  ]
</pre></code>
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

<a target='blank' style='color:#FFF !important' href="https://data.pa.gov/resource/fnrp-gye7.json?$select=dog_info_breed,count(dog_info_breed) AS breed_count&$group=dog_info_breed&$order=breed_count DESC"><code style=''>https://<span class="greenery">data.pa.gov</span>/resource/<span class="golden">fnrp-gye7</span>.<span class="blushing-salmon">json</span>$select=dog_info_breed,count(dog_info_breed) AS breed_count&$group=dog_info_breed&$order=breed_count DESC</code></a>

<pre><code data-trim contenteditable class="javascript">
  [
    {
      "breed_count": "1624",
      "dog_info_breed": "American Pit Bull Terrier"
    },
    {
      "breed_count": "675",
      "dog_info_breed": "MIXED BREED"
    },
    {
      "breed_count": "450",
      "dog_info_breed": "German Shepherd"
    },
    {
      "breed_count": "345",
      "dog_info_breed": "OTHER"
    },
    {
      "breed_count": "269",
      "dog_info_breed": "Rottweiler"
    },
    {
      "breed_count": "156",
      "dog_info_breed": "Labrador Retriever"
    },
    {
      "breed_count": "121",
      "dog_info_breed": "MIXED BREED: Pit Bull Mix"
    },
    {
      "breed_count": "117",
      "dog_info_breed": "Boxer"
    },, ... // and so on
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

- In person
- IRC: [chat.freenode.net/#socrata-soda](irc://chat.freenode.net/#socrata-soda)
- Stack Overflow: [soda](http://stackoverflow.com/questions/tagged/soda) or [socrata](http://stackoverflow.com/questions/tagged/socrata)

---

## Libraries &amp; SDKs

<img src="../../img/socrata-heart-opensource.png"/>

### [dev.socrata.com/libraries/](http://dev.socrata.com/libraries/)

<div class="footnote"><a href="http://socrata.github.io/soda-ruby/">Ruby</a>, <a href="https://github.com/socrata/soda-scala">Scala</a>, <a href="http://socrata.github.io/soda-java/">Java</a>, <a href="https://github.com/socrata/soda-ios-sdk">ObjectiveC</a>, <a href="https://github.com/Chicago/RSocrata">R</a>, <a href="https://github.com/socrata/soda-swift">Swift</a>, etc.</div>

===


<img class="fullscreen-img" src="/presentations/img/maggie.jpg"/>

# Thanks!
