<template>
  <div>
    <Header />
    <Nuxt />
    <Footer />
  </div>
</template>
 <script>
import Footer from "../components/Footer";
import Header from "../components/Header";
export default {
  components: {
    Footer,
    Header,
  },
};
</script>

<style>
html {
  font-family: "Source Sans Pro", -apple-system, BlinkMacSystemFont, "Segoe UI",
    Roboto, "Helvetica Neue", Arial, sans-serif;
  font-size: calc(10px + 0.35vw);
  word-spacing: 1px;
  -ms-text-size-adjust: 100%;
  -webkit-text-size-adjust: 100%;
  -moz-osx-font-smoothing: grayscale;
  -webkit-font-smoothing: antialiased;
  box-sizing: border-box;
  scroll-behavior: smooth;
}
html:focus-within {
  scroll-behavior: smooth;
}
*,
*::before,
*::after {
  box-sizing: border-box;
  margin: 0;
}
</style>
