<script setup>
import BarChart from "@/components/BarChart.vue";
import DoughnutChart from "@/components/Doughnut.vue";
//import LineChart from "@/components/LineChart.vue";
import GetRevisions from "@/components/GetRevisions.vue";

</script>

<template>
    <div class="box">
    <h2 class="title is-5">Bar Chart</h2>
      <BarChart /> <br/>
    <h2 class="title is-5">Circle Chart</h2>
    <DoughnutChart /> <br/>
    <h2 class="title is-5">Line Chart</h2>
    <LineChart /> <br/>
    <h2 class="title is-5">[Git Info Sample]</h2>
      <GetRevisions />
  </div>
</template>

<style scoped>
</style>
