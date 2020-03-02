## NYC Open Data Week
## Socrata OpenData APIs
![Socrata](img/ny-snu.png)
### Ori Pleban
### Data Integration Architect
### ori.pleban@tylertech.com

===

<h1>What the heck<br />is Socrata?</h1>
<!-- ![Tyler](img/tyler-transparent.png) -->

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

### Open Data NYC

![Open Data NYC Home Page](img/nyc_data.png)

---
### In the Catalog

![Open Data NYC Catalog](img/nyc_catalog.png)

---

## API Endpoints

<br />
<code style='font-size:120%;'>https://<span class="greenery">$domain</span>/resource/<span class="golden">$identifier</span>.<span class="blushing-salmon">$ext</span></code>

<br />

<p style='text-align: left; margin-left:50px;'><em>Where:</em></p>

- <code><span class="greenery">$domain</span></code> is the publisher's domain (ex: <code>data.cityofnewyork.us</code>)
- <code><span class="golden">$identifier</span></code> is a dataset's unique ID (ex: <code>tg4x-b46p</code>)
- <code><span class="blushing-salmon">$ext</span></code> is <code>json</code>, <code>csv</code>, <code>xml</code>, or <code>rdf</code>


---

## Example: LPC Individual Landmark and Historic District Building Database

<a target='blank' style='color:#FFF !important' href='https://data.cityofnewyork.us/resource/x3ar-yjn2.json'><code style=''>https://<span class="greenery">data.cityofnewyork.us</span>/resource/<span class="golden">x3ar-yjn2</span>.<span class="blushing-salmon">json</span></code></a>

<pre>
  <code data-trim contenteditable class="javascript">
[
  [
    {
        "bin": "3368915",
        "objectid": "1",
        "the_geom": {
            "type": "MultiPolygon",
            "coordinates": [
                [
                    [
                        [
                            -73.96005569077911,
                            40.630963850647355
                        ],
                        [
                            -73.9601274248611,
                            40.63095772769943
                        ],
                        [
                            -73.96013489308709,
                            40.631008513285295
                        ],
                        [
                            -73.96006315895082,
                            40.6310146371383
                        ],
                        [
                            -73.96005569077911,
                            40.630963850647355
                        ]
                    ]
                ]
            ]
        },
        "bbl": "3066920018",
        "doitt_id": "869806",
        "height_roo": "15.82",
        "ground_ele": "34",
        "borough": "BK",
        "block": "6692",
        "lot": "18",
        "zip_code": "11230",
        "address": "803 EAST 17 STREET",
        "owner_name": "HERRING, VINCENT",
        "num_floors": "2.75",
        "year_built": "1901",
        "year_alter_1": "0",
        "year_alter_2": "0",
        "des_addres": "803 East 17th Street",
        "circa": "1",
        "date_low": "1912",
        "date_high": "1912",
        "date_combo": "c. 1912",
        "alt_date_1": "1958",
        "alt_date_2": "0",
        "arch_build": "Seth Cutting (or) Adelsohn & Feinberg",
        "own_devel": "Stephen Norman",
        "alt_arch_1": "Donald A. Brown",
        "alt_arch_2": "0",
        "altered": "1",
        "style_prim": "Not determined",
        "style_sec": "0",
        "style_oth": "0",
        "non_contrib": "0",
        "mat_prim": "Wood Frame",
        "mat_sec": "Asphalt Shingles",
        "mat_third": "0",
        "mat_four": "0",
        "mat_other": "0",
        "use_orig": "Outbuilding, garage",
        "use_other": "0",
        "build_type": "Garage",
        "build_oth": "0",
        "build_nme": "0",
        "notes": "0",
        "new_const": "0",
        "hist_dist": "Fiske Terrace-Midwood Park Historic District",
        "era": "1901 - 1925",
        "lm_orig": "0",
        "lm_new": "0",
        "hd_flag": "1",
        "il_flag": "0",
        "bbl_2": "3066920018",
        "shape_leng": "77.3082905818",
        "shape_area": "373.033620654"
    },
    {
        "bin": "3384822",
        "objectid": "2",
        "the_geom": {
            "type": "MultiPolygon",
            "coordinates": [
                [
                    [
                        [
                            -73.95996028425891,
                            40.63088240239434
                        ],
                        [
                            -73.96002859598848,
                            40.63087498787182
                        ],
                        [
                            -73.96003493598042,
                            40.63090889283422
                        ],
                        [
                            -73.95996662421683,
                            40.630916307360515
                        ],
                        [
                            -73.95996028425891,
                            40.63088240239434
                        ]
                    ]
                ]
            ]
        },
        "bbl": "3066920074",
        "doitt_id": "958541",
        "height_roo": "16.24",
        "ground_ele": "34",
        "borough": "BK",
        "block": "6692",
        "lot": "74",
        "zip_code": "11230",
        "address": "814 EAST 18 STREET",
        "owner_name": "ADLER, BRUCE",
        "num_floors": "2.5",
        "year_built": "1925",
        "year_alter_1": "0",
        "year_alter_2": "0",
        "des_addres": "814 East 18th Street (aka 812-814 East 18th Street)",
        "circa": "0",
        "date_low": "0",
        "date_high": "0",
        "date_combo": "Not determined",
        "alt_date_1": "0",
        "alt_date_2": "0",
        "arch_build": "Not determined",
        "own_devel": "Not determined",
        "alt_arch_1": "0",
        "alt_arch_2": "0",
        "altered": "0",
        "style_prim": "Not determined",
        "style_sec": "0",
        "style_oth": "0",
        "non_contrib": "0",
        "mat_prim": "Brick",
        "mat_sec": "0",
        "mat_third": "0",
        "mat_four": "0",
        "mat_other": "0",
        "use_orig": "Outbuilding, garage",
        "use_other": "0",
        "build_type": "Garage",
        "build_oth": "0",
        "build_nme": "0",
        "notes": "Shared garage with 818 East 18th Street.",
        "new_const": "0",
        "hist_dist": "Fiske Terrace-Midwood Park Historic District",
        "era": "Not determined",
        "lm_orig": "0",
        "lm_new": "0",
        "hd_flag": "1",
        "il_flag": "0",
        "bbl_2": "3066920074",
        "shape_leng": "63.2596692328",
        "shape_area": "238.971308005"
    },... and so on
]
  </code>
</pre>

---

## Simple Filters

<a target='blank' style='color:#FFF !important' href='https://data.cityofnewyork.us/resource/x3ar-yjn2.json?style_prim=Italianate'><code style=''>https://<span class="greenery">data.cityofnewyork.us</span>/resource/<span class="golden">x3ar-yjn2</span>.<span class="blushing-salmon">json</span>
<br />?<span class="toy-store-blue">category</span>=<span style="color:MediumOrchid">Italianate</span></code></a>

<pre><code data-trim contenteditable class="javascript">
[
    {
        "bin": "3055294",
        "objectid": "18",
        "the_geom": {
            "type": "MultiPolygon",
            "coordinates": [
                [
                    [
                        [
                            -73.96820179856762,
                            40.68894483760301
                        ],
                        [
                            -73.96824591342943,
                            40.688939827621134
                        ],
                        [
                            -73.96836709675894,
                            40.68892606693165
                        ],
                        ...
                    ]
                ]
            ]
        },
        "bbl": "3019290031",
        "doitt_id": "426989",
        "height_roo": "41.32",
        "ground_ele": "93",
        "borough": "BK",
        "block": "1929",
        "lot": "31",
        "zip_code": "11205",
        "address": "306 CLINTON AVENUE",
        "owner_name": "QUELLE, GEOFFREY",
        "num_floors": "3",
        "year_built": "1899",
        "year_alter_1": "2005",
        "year_alter_2": "0",
        "des_addres": "306 Clinton Avenue",
        ...
    },
    {
        "bin": "3058486",
        "objectid": "22",
        "the_geom": {
            "type": "MultiPolygon",
            "coordinates": [
                [
                    [
                        [
                            -73.97196672828584,
                            40.69026295754327
                        ],
                        [
                            -73.97196880699245,
                            40.69026272391617
                        ],...
                    ]
                ]
            ]
        },
        "bbl": "3020900011",
        "doitt_id": "84178",
        "height_roo": "48.04",
        "ground_ele": "66",
        "borough": "BK",
        "block": "2090",
        "lot": "11",
        "zip_code": "11205",
        "address": "249 CARLTON AVENUE",
        "owner_name": "GEHRING, KATHRINE A",
        "num_floors": "4",
        "year_built": "1930",
        "year_alter_1": "2009",
        "year_alter_2": "0",
        "des_addres": "249 Carlton Avenue",
        ...

    },
    {
        "bin": "3003319",
        "objectid": "33",
        "the_geom": {
            "type": "MultiPolygon",
            "coordinates": [
                [
                    [
                        [
                            -73.99864515073207,
                            40.687764307484464
                        ],
                        [
                            -73.99867459780505,
                            40.68771259403958
                        ],...
                    ]
                ]
            ]
        },
        "bbl": "3003050040",
        "doitt_id": "450463",
        "height_roo": "34.21",
        "ground_ele": "19",
        "borough": "BK",
        "block": "305",
        "lot": "40",
        "zip_code": "11201",
        "address": "141 BALTIC STREET",
        "owner_name": "ALICE H HIROMURA",
        "num_floors": "3",
        "year_built": "1899",
        "year_alter_1": "0",
        "year_alter_2": "0",
        "des_addres": "141 Baltic Street",
        ...
    }
]
</code></pre>

---

## SoQL Queries
<a href="https://data.cityofnewyork.us/resource/x3ar-yjn2.json?$select=bin, style_prim, borough, year_built, address, zip_code&$where=year_built < 1900 AND borough = 'BK'"><code>https://data.cityofnewyork.us/resource/tg4x-b46p.json?<span class="toy-store-blue">$select</span>=<span class="golden">bin, style_prim, borough, year_built, address, zip_code</span>&<span class="toy-store-blue">$where</span>=<span class="golden">year_built < '1900' AND borough ='BK'</span></code></a>

<pre><code data-trim contenteditable class="javascript">
[
  {
      "bin": "3179095",
      "style_prim": "Colonial Revival with alterations",
      "borough": "BK",
      "year_built": "1899",
      "address": "1704 GLENWOOD ROAD",
      "zip_code": "11230"
  },
  {
      "bin": "3055294",
      "style_prim": "Italianate",
      "borough": "BK",
      "year_built": "1899",
      "address": "306 CLINTON AVENUE",
      "zip_code": "11205"
  },
  {
      "bin": "3018635",
      "style_prim": "Romanesque Revival",
      "borough": "BK",
      "year_built": "1899",
      "address": "19 ST MARKS AVENUE",
      "zip_code": "11217"
  },
  {
      "bin": "3003319",
      "style_prim": "Italianate",
      "borough": "BK",
      "year_built": "1899",
      "address": "141 BALTIC STREET",
      "zip_code": "11201"
  },
  {
      "bin": "3058779",
      "style_prim": "Transitional Italianate / neo-Grec",
      "borough": "BK",
      "year_built": "1899",
      "address": "63 SOUTH ELLIOTT PLACE",
      "zip_code": "11217"
  }, ...
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

<a href="https://data.cityofnewyork.us/resource/x3ar-yjn2.json?$select=borough, count(*) as number_of_landmarks&$group=borough">
  <code>https://data.cityofnewyork.us/resource/x3ar-yjn2.json?
    <span class="toy-store-blue">$select</span>=
    <span class="golden">borough, count(*) as number_of_landmarks</span>
    <span class="toy-store-blue">$group</span>=
    <span class="golden">borough</span>
  </code>
</a>

<pre><code data-trim contenteditable class="javascript">
[
  {
      "number_of_landmarks": "1"
  },
  {
      "borough": "BK",
      "number_of_landmarks": "16259"
  },
  {
      "borough": "MN",
      "number_of_landmarks": "14167"
  },
  {
      "borough": "bk",
      "number_of_landmarks": "1"
  },
  {
      "borough": "0",
      "number_of_landmarks": "1"
  },
  {
      "borough": "BX",
      "number_of_landmarks": "1036"
  },
  {
      "borough": "SI",
      "number_of_landmarks": "536"
  },
  {
      "borough": "QN",
      "number_of_landmarks": "4656"
  }
]
</code></pre>

---

## Geospatial Queries
  <a target='blank' style='color:#FFF !important' href="https://data.cityofnewyork.us/resource/x3ar-yjn2.json?$select=bin,year_built,style_prim&$where=within_circle(the_geom,40.712,-74.004,500)"><code style=''>https://<span class="greenery">data.cityofnewyork.us</span>/resource/<span class="golden">x3ar-yjn2</span>.<span class="blushing-salmon">json</span>
  <br />?<span class="toy-store-blue">$where=</span><span style="color:MediumOrchid">within_circle(the_geom,40.712,-74.004,500)</span></code></a>

  <pre><code data-trim contenteditable class="javascript">
[
  {
      "bin": "1001218",
      "borough": "MN",
      "year_built": "1910",
      "style_prim": "Francois Premier",
      ...
  },
  {
      "bin": "1001380",
      "borough": "MN",
      "year_built": "1920",
      "style_prim": "Vernacular",
      ...
  },
  {
      "bin": "1001382",
      "borough": "MN",
      "year_built": "1900",
      "style_prim": "Not determined",
      ...
  },
  {
      "bin": "1001348",
      "borough": "MN",
      "year_built": "1900",
      "style_prim": "Greek Revival",
      ...
  }, ...
]
  </code></pre>

---
## Paging Through Data

<a target='_blank' style='color:#FFF !important' href='https://data.cityofnewyork.us/resource/x3ar-yjn2.json?$limit=5&$offset=10'><code style=''>https://<span class="greenery">data.cityofnewyork.us</span>/resource/<span class="golden">x3ar-yjn2</span>.<span class="blushing-salmon">json</span>
<br />?<span class="toy-store-blue">$limit</span>=<span style="color:MediumOrchid">5</span>&<span class="toy-store-blue">$offset</span>=<span style="color:MediumOrchid">10</span></code></a>

---

## SoQL Function Listing

<a target='_blank' style='color:#FFF !important' href='https://dev.socrata.com/docs/functions/'>

---

## Application Tokens

1. Register at [https:/data.cityofnewyork.us/profile/app_tokens](https://data.cityofnewyork.us/profile/app_tokens)
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
