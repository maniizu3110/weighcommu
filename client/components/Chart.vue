<template>
  <div>
    <h1>Report</h1>
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
        labels: ['12/5', '12/6', '12/7', '12/8','12/9','12/10','12/11','12/5', '12/6', '12/7', '12/8','12/9','12/10','12/11','12/5', '12/6', '12/7', '12/8','12/9','12/10','12/11','12/5', '12/6', '12/7', '12/8','12/9','12/10','12/11'],
        datasets: [
          {
            pointBackgroundColor:'#4bcc96',
            label: 'Weight',
            borderColor: '#4bcc96',
            borderWidth: 4,
            fill: false,
            data: [54,53,52,53,52,54,53,52,53,52,54,53,52,53,54.4,52,54,53,52,53,57,52,54,53,52,53,57,52],
          },
        ],
      },
      chartOptions: {
        maintainAspectRatio: false,
        responsive: true,
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
