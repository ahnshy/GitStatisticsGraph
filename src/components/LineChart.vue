<template>
  <div>
    <LineChart :chart-data="chartData" />
  </div>
</template>

<script>
import { Line } from 'vue-chartjs';
import { Chart, registerables } from 'chart.js';
Chart.register(...registerables);

export default {
  components: {
    LineChart: {
      extends: Line,
      props: ['chartData'],
      mounted() {
        this.renderChart(this.chartData, {
          responsive: true,
          maintainAspectRatio: false,
        });
      },
    },
  },
  data() {
    return {
      chartData: {
        labels: [], // Dates
        datasets: [
          {
            label: 'Commits per Day',
            backgroundColor: '#f87979',
            data: [], // Number of commits per day
          },
        ],
      },
    };
  },
  mounted() {
    this.fetchGitLogData();
  },
  methods: {
    fetchGitLogData() {
      // Replace this with the actual Git log output or fetch logic
      const gitLogOutput = `
2024-01-10 : Fixed bug in authentication
2024-01-12 : Updated README
2024-02-05 : Added new feature
2024-02-05 : Updated documentation
2024-03-01 : Refactored code
      `;

      const commitsPerDay = {};

      gitLogOutput.trim().split('\n').forEach(line => {
        const [date, ] = line.split(' : ');
        if (!commitsPerDay[date]) {
          commitsPerDay[date] = 0;
        }
        commitsPerDay[date] += 1;
      });

      this.chartData.labels = Object.keys(commitsPerDay);
      this.chartData.datasets[0].data = Object.values(commitsPerDay);
    },
  },
};
</script>

<style scoped>
.chart-container {
  position: relative;
  height: 40vh;
  width: 80vw;
}
</style>
