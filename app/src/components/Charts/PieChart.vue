<template>
  <svg width="500" height="400"></svg>
</template>

<script>
import * as d3 from "d3";
export default {
  name: "PieChart",
  props: {
    btc: {
      type: Number,
      required: true
    },
    eth: {
      type: Number,
      required: true
    }
  },
  mounted() {

    var svg = d3.select("svg"),
        width = svg.attr("width"),
        height = svg.attr("height"),
        radius = 200;

    // Create data
    var data = [
        {name: "BTC", share: this.btc},
        {name: "ETH", share: this.eth},
        {name: "Rest", share: 100 - (42.3 + 19.6)},
        ];

    var g = svg.append("g")
        .attr("transform", "translate(" + width / 2 + "," + height / 2 + ")");

    var ordScale = d3.scaleOrdinal()
        .domain(data)
        .range(['#60a0b0','#9ad1aa','#e97a7a']);

    var pie = d3.pie().value(function(d) {
      return d.share;
    });


    var arc = g.selectAll("arc")
        .data(pie(data))
        .enter();

    var path = d3.arc()
        .outerRadius(radius)
        .innerRadius(radius * 0.6);

    arc.append("path")
        .attr("d", path)
        .attr("fill", function(d) { return ordScale(d.data.name); })
        .attr('stroke', 'white')
        .style('stroke-width', '10px')
        .style('opacity', 0.7);

    var label = d3.arc()
        .outerRadius(radius)
        .innerRadius(radius * 0.55);

    arc.append("text")
        .attr("transform", function(d) {
          return "translate(" + label.centroid(d) + ")";
        })
        .text(function(d) { return d.data.name; })
        .style("font-family", "arial")
        .style("font-size", 20);
  }
}
</script>

<style scoped>

</style>
