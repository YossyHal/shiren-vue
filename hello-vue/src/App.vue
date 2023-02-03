<script setup lang="ts">
import DemoGrid from "./components/GridSearch.vue";
import { ref } from "vue";

const searchQuery = ref("");
const gridColumns = ["name", "power"];
interface GridDataInterface {
  name: string;
  power: number;
  [key: string]: string | number;
}
const gridData = [
  { name: "Chuck Norris", power: Infinity } as GridDataInterface,
  { name: "Bruce Lee", power: 9000 } as GridDataInterface,
  { name: "Jackie Chan", power: 7000 } as GridDataInterface,
  { name: "Jet Li", power: 8000 } as GridDataInterface,
];
</script>

<template>
  <form id="search">Search <input name="query" v-model="searchQuery" /></form>
  <DemoGrid :data="gridData" :columns="gridColumns" :filter-key="searchQuery">
  </DemoGrid>
</template>
