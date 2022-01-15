<template>
  <main class="wrapper">
    <HeaderScam/>
    <PostHeader/>
    <CheckedInputs/>
  </main>
</template>

<script>
// import { data, textInFlags } from "@/data.js";
//components
import HeaderScam from "@/components/HeaderScam.vue";
import PostHeader from "@/components/PostHeader.vue";
import CheckedInputs from "@/components/CheckedInputs.vue";

export default {
  name: "App",
  components: {
    HeaderScam,
    PostHeader,
    CheckedInputs,
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
}
.wrapper{
  max-width: 1600px;
  margin: 0 auto;
}




</style>
