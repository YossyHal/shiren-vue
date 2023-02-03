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
  { name: "あかりの巻物", power: 100 } as GridDataInterface,
  { name: "オイルの巻物", power: 100 } as GridDataInterface,
  { name: "識別の巻物", power: 200 } as GridDataInterface,
  { name: "集合の巻物", power: 300 } as GridDataInterface,
];
</script>

<template>
  <form id="search">Search <input name="query" v-model="searchQuery" /></form>
  <DemoGrid :data="gridData" :columns="gridColumns" :filter-key="searchQuery">
  </DemoGrid>
</template>
