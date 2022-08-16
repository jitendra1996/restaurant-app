<template>
  <div>
    <Html>
      <Head>
        <Title>Top 50-restaurants in the world</Title>
      </Head>
    </Html>
    <NuxtLayout name="custom">
      <div class="text-center mt-5">
        <h1 class="mb-5">Top 50 Restaurants</h1>
        <hr class="w-3/4 m-auto mb-5" />
        <div class="flex align-middle w-4/5 m-auto">
          <div class="w-1/2 m-auto text-center">
            <Rows :isHeader="true" />
            <Rows
              v-for="(res, index) in organisedData.first"
              :key="res.id"
              v-bind="res"
              :index="index"
            />
          </div>
          <div class="w-1/2 m-auto">
            <Rows :isHeader="true" />
            <Rows
              v-for="(nxtRes, index) in organisedData.second"
              :key="nxtRes.id"
              v-bind="nxtRes"
              :index="index"
            />
          </div>
        </div>
      </div>
    </NuxtLayout>
  </div>
</template>

<script setup lang="ts">
import resturants from "@/data.json";

const organisedData = {
  first: [...resturants].splice(0, 25),
  second: [...resturants].splice(25, 25),
};
</script>
