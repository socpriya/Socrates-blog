---
layout: post
title: Visulization of data using googleVis 
---

This is my attempt to visualize data using googleVis.

<!-- jsHeader -->
<script type="text/javascript">
 
// jsData 
function gvisDataMotionChartID20b09e65ef7 () {
var data = new google.visualization.DataTable();
var datajson =
[
 [
 "",
new Date(,,),
"",
,
,
 
] 
];
data.addColumn('string','type');
data.addColumn('date','date');
data.addColumn('string','user_type');
data.addColumn('number','period');
data.addColumn('number','counts');
data.addColumn('number','user_count');
data.addRows(datajson);
return(data);
}
 
// jsDrawChart
function drawChartMotionChartID20b09e65ef7() {
var data = gvisDataMotionChartID20b09e65ef7();
var options = {};
options["width"] = [800];
options["height"] = [600];
options["state"] = {"xAxisOption":"TIME", "xLambda":1};


    var chart = new google.visualization.MotionChart(
    document.getElementById('MotionChartID20b09e65ef7')
    );
    chart.draw(data,options);
    

}
  
 
// jsDisplayChart
(function() {
var pkgs = window.__gvisPackages = window.__gvisPackages || [];
var callbacks = window.__gvisCallbacks = window.__gvisCallbacks || [];
var chartid = "motionchart";
  
// Manually see if chartid is in pkgs (not all browsers support Array.indexOf)
var i, newPackage = true;
for (i = 0; newPackage && i < pkgs.length; i++) {
if (pkgs[i] === chartid)
newPackage = false;
}
if (newPackage)
  pkgs.push(chartid);
  
// Add the drawChart function to the global list of callbacks
callbacks.push(drawChartMotionChartID20b09e65ef7);
})();
function displayChartMotionChartID20b09e65ef7() {
  var pkgs = window.__gvisPackages = window.__gvisPackages || [];
  var callbacks = window.__gvisCallbacks = window.__gvisCallbacks || [];
  window.clearTimeout(window.__gvisLoad);
  // The timeout is set to 100 because otherwise the container div we are
  // targeting might not be part of the document yet
  window.__gvisLoad = setTimeout(function() {
  var pkgCount = pkgs.length;
  google.load("visualization", "1", { packages:pkgs, callback: function() {
  if (pkgCount != pkgs.length) {
  // Race condition where another setTimeout call snuck in after us; if
  // that call added a package, we must not shift its callback
  return;
}
while (callbacks.length > 0)
callbacks.shift()();
} });
}, 100);
}
 
// jsFooter
</script>
 
<!-- jsChart -->  
<script type="text/javascript" src="https://www.google.com/jsapi?callback=displayChartMotionChartID20b09e65ef7"></script>
 
<!-- divChart -->
  
<div id="MotionChartID20b09e65ef7" 
  style="width: 800; height: 600;">
</div>

<br>


![screenshot]({{ site.baseurl }}/assets/img/underscore.png)