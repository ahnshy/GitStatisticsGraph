<script setup>
import BarChart from "@/components/BarChart.vue";
import DoughnutChart from "@/components/Doughnut.vue";
import LineChart from "@/components/LineChart.vue";

</script>

<template>
    <div class="box">
    <h2 class="title is-5">Bar Chart</h2>
      <BarChart />
      <br/><h2 class="title is-5">Circle Chart</h2>
      <DoughnutChart />
      <br/><h2 class="title is-5">Line Chart</h2>
      <LineChart />
  </div>
</template>

<style scoped>
</style>
