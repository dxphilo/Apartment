<template>
  <div>
    <!-- landing page component -->
    <Landing />
    <Houses />
  </div>
</template>
 <script>
//  landingpage component
const Landing = () =>
  import(/*webpackChunkName: "Landingcomponent"*/ "@/components/Landing");
const Houses = () =>
  import(/*webpackChunkName: "Houses"*/ "@/components/Houses");
export default {
  components: {
    Landing,
    Houses,
  },
};
</script>
<style scoped>
</style>