<template>
  <Doughnut :data="chartData" />
</template>

<script>
import { Doughnut } from 'vue-chartjs'
import {Chart as ChartJS, Title, Tooltip, Legend, BarElement, CategoryScale, LinearScale} from 'chart.js'

ChartJS.register(Title, Tooltip, Legend, BarElement, CategoryScale, LinearScale)

export default {
  name: 'BarChart',
  components: {Doughnut},
  computed: {
    myStyles() {
      return {
        height: `500px`,
        position: 'relative'
      }
    }
  },
  data() {
    return {
      chartData: {
        labels: ['January', 'February', 'March'],
        datasets: [
          {
            label: 'Monthly Use',
            backgroundColor: ['#f89d00', '#067a03', '#009fff', '#E46651'],
            // backgroundColor: '#f87979',
            data: [40, 20, 12]
          }
        ]
      }
    }
  }
}
</script>
