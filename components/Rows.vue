<template>
  <div v-if="isHeader" class="flex w-11/12 m-auto rounded-full">
    <h4 class="p-5 w-1/4">Rank</h4>
    <h4 class="p-5 w-3/4">Chain</h4>
  </div>
  <div
    v-else
    :class="[
      index % 2 === 0 ? 'bg-slate-600 text-white' : '',
      'flex',
      'w-11/12',
      'm-auto',
      'rounded-full',
    ]"
  >
    <h4 class="p-5 w-1/4">{{ id }}</h4>
    <a :href="`/restaurants/${name}`" class="p-5 w-3/4">{{ name }}</a>
  </div>
</template>

<script setup lang="ts">
interface RowsData {
  id?: number;
  rank?: number;
  index?: number;
  name?: String;
  content?: String;
  revenue?: number;
  numberOfStores?: String;
  imageUrl?: String;
  isHeader?: boolean;
}
const data = defineProps<RowsData>();
</script>
