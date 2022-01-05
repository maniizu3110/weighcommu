<template>
  <div>
    <h1>Vue Chart</h1>
    <div class="chart-div">
      <LineChart
        :chartData="chartData"
        :options="chartOptions"
        class="line-chart"
      />
    </div>
  </div>
</template>
<script>
export default {
  data() {
    return {
      chartData: {
        labels: ['12/5', '12/6', '12/7', '12/8','12/9','12/10','12/11'],
        datasets: [
          {
            label: 'Numbers',
            borderColor: '#4bcc96',
            borderWidth: 4,
            fill: false,
            data: [54,53,52,53,,60,52],
          },
        ],
      },
      chartOptions: {
        maintainAspectRatio: false,
        responsive: true,
        tooltips:{
          titleFontColor:"303030",
        
        },
      },
    }
  },
}
</script>
<style>
.line-chart {
  width: 75vw;
  height: 50vh;
}
</style>
