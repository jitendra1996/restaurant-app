<template>
  <NuxtLayout name="custom">
    <div class="w-4/5 m-auto p-5" v-if="restaurantDetails">
      <h1>{{ restaurantDetails.name }}</h1>
      <hr />
      <div class="flex items-center">
        <div class="w-1/2 p-5">
          <img
            :src="restaurantDetails.imageUrl"
            :alt="restaurantDetails.name"
          />
        </div>
        <div class="w-1/2 p-5">
          <h3>Rank : {{ restaurantDetails.rank }}</h3>
          <div>Number of Stores : {{ restaurantDetails.numberOfStores }}</div>
          <div>Revenue (in billions) : ${{ restaurantDetails.revenue }}</div>
          <div>{{ restaurantDetails.content }}</div>
        </div>
      </div>
    </div>
    <div v-else class="m-auto text-center mt-10 h-96">
      <NuxtLayout name="error">
        <template #header>
          <h1 class="mb-5">Restaurant not Found</h1>
        </template>
        <template #redirectLink>
          <a href="/restaurants/">Go Back</a>
        </template>
      </NuxtLayout>
    </div>
  </NuxtLayout>
</template>

<script setup lang="ts">
import {} from "#app";
import restaurants from "@/data.json";

const route = useRoute();
const name = route.params.name;
const restaurantDetails = restaurants.find((el) => name === el.name);

if (restaurantDetails) {
  useMeta({
    title: restaurantDetails.name
      ? restaurantDetails.name
      : "404 - Restaurant Not Found",
    meta: [
      {
        name: "viewport",
        content: "width=device-width",
      },
    ],
  });
}
</script>
