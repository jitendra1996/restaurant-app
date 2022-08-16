<template>
  <div>
    <Html :lang="dynamic > 50 ? 'en-GB' : 'en-US'">
      <Head>
        <Title>Restaurants</Title>
      </Head>
    </Html>
    <div class="text-center mt-20">
      <h1 class="text-2xl font-sans uppercase font-light tracking-widest">
        Welcome to Restaurantly
      </h1>
      <a href="/restaurants">list of Restaurants</a>
    </div>
  </div>
</template>

<script setup lang="ts">
const dynamic = ref(90);
</script>
