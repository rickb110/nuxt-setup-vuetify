<template>
<!-- example map here -->
	
	<div class="chart" id="regions_div"> </div>

<script type="text/javascript" src="https://www.gstatic.com/charts/loader.js"></script>
<script type="text/javascript">
google.charts.load('current', {'packages':['geochart', 'corechart']});
google.charts.setOnLoadCallback(drawRegionsMap);
google.charts.setOnLoadCallback(drawChart);

function drawRegionsMap() {
 var data = google.visualization.arrayToDataTable([
          ['Country', 'Customer Count', 'Agent Count'],
          ['Argentina', 999000, 100],
          ['Australia', 969000, 450],
          ['Belgium', 12000, 200],
          ['Brazil', 850000, 250],
          ['Canada', 1110000, 590],
          ['China', 3975000, 690],
          ['Colombia', 4500, 100],
          ['Denmark', 78600, 150],
          ['France', 67000, 400],
          ['Germany', 140000, 550],
          ['India', 1060000, 560],
          ['Japan', 60000, 420],
          ['Nigeria', 1054000, 305],
          ['Philippines', 120000, 230],
          ['Russia', 2904000, 180],
          ['Singapore', 79000, 450],
          ['South Korea', 15000, 290],
          ['Switzerland', 35000, 230],
          ['United Kingdom', 4015000, 750],
          ['United States', 5000500, 1500],
]);

var options = {
colorAxis: {colors: ['#eee8f3', '#ddd1e7','#ccbadc','#bba3d0','#aa8cc5','#9975b9','#885ead', '#7647a2', '#663096', '#551a8b']},
legend: 'none',
};

var chart = new google.visualization.GeoChart(document.getElementById('regions_div'));
chart.draw(data, options);
}
</script>
	<!-- end of example map -->
</template>

<style lang="scss">
.bottom-footer {
  background: #e3f2ed;
  padding: 40px 0 120px 0;
  text-align: center;
}

.bottom-footer__link {
  color: #8ba19a;
  text-decoration: none;
}
</style>