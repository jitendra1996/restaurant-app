<template>
  <div>
    <Html>
      <Head>
        <Title>404 - Page Not Found</Title>
      </Head>
    </Html>
    <div class="text-center mt-20">
      <NuxtLayout name="error">
        <template #header>
          <h1 class="text-2xl font-sans uppercase font-light tracking-widest">
            Page Not Found
          </h1>
        </template>
        <template #redirectLink>
          <a href="/restaurants">Go Back To Restaurants</a>
        </template>
      </NuxtLayout>
    </div>
  </div>
</template>
