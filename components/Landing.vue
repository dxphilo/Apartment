<template>
  <!-- landing page component -->
  <div class="w-full landing bg-center bg-no-repeat bg-cover object-cover">
    <div class="text-center pt-48">
      <h1 class="text-6xl font-bold">Kijiji Housing</h1>
      <P class="text-2xl text-gray-800">Find available apartments in Eldoret</P>
    </div>
  </div>
</template>
 <script>
export default {};
</script>
<style scoped>
.landing {
  background-image: url("../assets/2.webp"),
    linear-gradient(rgba(0, 0, 0, 0.514), rgba(0, 0, 0, 0.514));
  height: 500px;
}
@media (max-width: 900px) {
  .landing {
    height: 300px;
  }
}
</style>