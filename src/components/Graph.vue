<canvas id="Chart" width="400" height="400"></canvas>
<script>
var xValues = [Wk1,Wk2,Wk3,Wk4,Wk5,Wk6,Wk7,Wk8,Wk9,wk10];
var yValues = [0,1,2,3,4,5,6,7,8,9,10];

new Chart("myChart", {
  type: "line",
  data: {
    labels: xValues,
    datasets: [{
      fill: false,
      lineTension: 0,
      backgroundColor: "rgba(0,0,255,1.0)",
      borderColor: "rgba(0,0,255,0.1)",
      data: yValues
    }]
  },
  options: {
    legend: {display: false},
    scales: {
      yAxes: [{ticks: {min: 6, max:16}}],
    }
  }
});
</script>
