<template>
  <div class="wrapper">
    <ul class="list">
      <li v-for="risk in risks" :key="risk.id">
        <input type="checkbox" name="risk" id="checkbox" />
        <label for="risk"> {{ risk }}</label>
      </li>
    </ul>
  </div>
</template>

<script>
// import List from '@/components/List.vue';

export default {
  name: "App",
  components: {
    // List,
  },
  data() {
    return {
      risks: [
        "upozornenie Národnej banky Slovenska, prípadne inej verejnej autority na aktivity takého subjektu",
        "vedenie súdneho alebo administratívneho konania proti poskytovateľovi služieb",
        "potreba zadať, zdieľať alebo komukoľvek poslať privátne kľúče, či heslo od peňaženky alebo účtu",
        "poskytovateľ služby garantuje ziskovosť alebo návratnosť investície (osobitne v krátkom časovom horizonte)",
        "použitie lákavých fráz „zarábajte online“ alebo „pasívny príjem“",
        "veľkolepé tvrdenia o vlastnom kryptoaktíve „nový Bitcoin/lepší ako Bitcoin“ s garantovaním budúceho zhodnotenia",
        "požiadavky na realizáciu ďalšej investície, pre účely výberu skoršej investície",
        "požiadavky na zaslanie kryptoaktív na neznáme adresy peňaženiek alebo na neznáme adresy bankových účtov, ktoré nie sú asociované s poskytovateľom predmetných služieb",
      ],
    };
  },
};
</script>

<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
#app {
  /* font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px; */
}
#checkbox{
  margin: .5rem;
}
</style>
