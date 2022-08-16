<template>
  <div>
    <Html>
      <Head>
        <Title>404 - Page Not Found</Title>
      </Head>
    </Html>
    <slot name="header" />
    <div>
      <img
        src="@/assets/images/icons8-sad-face-64.png"
        alt="sad emoji"
        class="m-auto p-10"
      />
    </div>
    <slot name="redirectLink" />
  </div>
</template>
