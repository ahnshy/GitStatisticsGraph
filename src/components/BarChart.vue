<template>
  <Bar :data="chartData" />
</template>

<script>
import { simpleGit } from 'simple-git';
import {Bar} from 'vue-chartjs'
import {Chart as ChartJS, Title, Tooltip, Legend, BarElement, CategoryScale, LinearScale} from 'chart.js'

ChartJS.register(Title, Tooltip, Legend, BarElement, CategoryScale, LinearScale)

export default {
  name: 'BarChart',
  components: {Bar},
  computed: {
    myStyles () {
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
            backgroundColor: ['#41B883', '#00D8FF', '#DD1B16', '#E46651'],
            // backgroundColor: '#f87979',
            data: [40, 20, 12]
          }
        ]
      }
    }
  }
}
</script>



<!--export default {-->
<!--name: 'BarChart',-->
<!--components: { Bar },-->
<!--data: () => ({-->
<!--loaded: false,-->
<!--chartData: null-->
<!--}),-->
<!--async mounted () {-->
<!--this.loaded = false-->

<!--try {-->
<!--const { userlist } = await fetch('/api/userlist')-->
<!--this.chartdata = userlist-->

<!--this.loaded = true-->
<!--} catch (e) {-->
<!--console.error(e)-->
<!--}-->
<!--}-->
<!--}-->
<!--</script>-->
