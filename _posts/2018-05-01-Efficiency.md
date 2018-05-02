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

<script src="/assets/bower_components/requirejs/require.js"></script>
<link href="/assets/src/d3_exploding_boxplot.css" rel="stylesheet" type="text/css"></link>
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
## Price movements.
The graph below shows the change in price of total goals markets using Pinnacle's opening & closing prices.  Each data point represents a game in which a selection has shortened in price.  I wanted to see whether there was any difference between the main European leagues.
#### Click on box to see individual game, double click whitespace to revert.
<div id="chartContainer">
</div>
#### Disclaimer: Data is scraped so opening price may not necesssarily have been the first price shown.
