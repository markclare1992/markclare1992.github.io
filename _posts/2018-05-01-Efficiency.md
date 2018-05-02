---
title: "Which league to bet on?"
date: 2018-05-01
layout: single
excerpt: Betting market efficiency.
categories:
  - Football
tags:
  - football
  - betting
  - total goals
comments: true
---
<style>
.axis text {
  font: 12px Open Sans;
  text-anchor: middle;
  letter-spacing: 1px;
}

.axis path,
.axis line {
  fill: none;
  stroke: #000000;
  shape-rendering: crispEdges;Disclaimer
}

.axis text {
  fill: none;
  stroke: #eaeaea;
  shape-rendering: crispEdges;
}


.x.axis path {
  /*display: none;*/
}

rect.d3-exploding-boxplot.box{
  /*opacity: 0.8;*/
}

line.d3-exploding-boxplot.line,
rect.d3-exploding-boxplot.box
{
  stroke: #000000;
  stroke-width: 1px;
}

line.d3-exploding-boxplot.vline{
  stroke-dasharray:5,5;
}

.d3-exploding-boxplot.tip{
  font: normal 13px 'Lato', 'Open sans', sans-serif;
  line-height: 1;
  font-weight: bold;
  padding: 12px;
  background: #333333;
  color: #DDDDDD;
  border-radius: 2px;
}

g.tick text,
g.axis text{
  -webkit-user-select: none;
  -khtml-user-select: none;
  -moz-user-select: none;
  -o-user-select: none;
  user-select: none;
  cursor: default;
}
</style>



## Price movements.
The graph below shows the change in price of total goals markets using Pinnacle's opening & closing prices.  Each data point represents a game in which a selection has shortened in price.  I wanted to see whether there was any drastic difference in efficiency across the main European leagues.
#### Click on box to see individual games, double click whitespace to revert.
<div id="chartContainer">
</div>
#### Disclaimer: Data is scraped so opening price may not necesssarily have been the first price shown.

[**D3 code for exploding boxplot from mcaule**](https://mcaule.github.io/d3_exploding_boxplot/)

<script src="/assets/bower_components/requirejs/require.js"></script>
<script type="text/javascript">
    require.config({
        baseUrl: ".",
        paths: {
            d3: '/assets/bower_components/d3/d3.min',
            "d3-tip": '/assets/bower_components/d3-tip/index',
            'd3-exploding-boxplot': '/assets/src/d3_exploding_boxplot'
        },
        shim: {
            'd3-exploding-boxplot': {
                deps: ['d3', 'd3-tip']
            },
            'd3-tip': {
                deps: ['d3']
            }
        }
    });
</script>
<script>
    require(['d3-exploding-boxplot', 'd3'], function(exploding_boxplot, d3) {
        d3.json("/assets/d3data.json", function(data) {
            var chart = exploding_boxplot(data['data'], {
                y: 'percentage_change',
                group: 'league',
                color: 'league',
                label_1: 'game',
                label_2: 'line',
                label_3: 'selection',
                label_4: 'open',
                label_5: 'close'
            });
            chart('#chartContainer');
        });
        d3.select("body").style("background-color", "#252a34");
    });
</script>


