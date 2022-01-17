<template>
  <HeaderScam/>

  <main class="wrapper">
    <PostHeader/>
    <CheckedInputs/>
    <Warning />
  </main>

  <FooterScam />
</template>

<script>
// import { data, textInFlags } from "@/data.js";
//components
import HeaderScam from "@/components/HeaderScam.vue";
import PostHeader from "@/components/PostHeader.vue";
import CheckedInputs from "@/components/CheckedInputs.vue";
import Warning from "@/components/Warning.vue";
import FooterScam from "@/components/FooterScam.vue";

export default {
  name: "App",
  components: {
    HeaderScam,
    PostHeader,
    CheckedInputs,
    Warning,
    FooterScam,
  },

};

</script>

<style >
@import url('https://fonts.googleapis.com/css2?family=IBM+Plex+Sans:wght@400;500;700&display=swap');
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
html{
  font-family: 'IBM Plex Sans', sans-serif;
}
body{
  color: #E5E5E5;
}

#app {
  /* margin: 0.625rem; */
  max-width: 1600px;
  margin: 0 auto;
}
.wrapper{
  max-width: 1600px;
  margin: 0 auto;
}




</style>
