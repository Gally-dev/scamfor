<template>
  <ul class="list">
    <li v-for="risk in risks" :key="risk.id" class="risk">
      <input
        ref="checkbox"
        type="checkbox"
        name="risk"
        id="checkbox"
        @click="check(); changeColor();"
      />
      <label for="risk"> {{ risk }}</label>
    </li>
  </ul>

  <div class="scamFor" ref="scamFor">
    <p>{{ changeText() }}</p> 
  </div>

  <flags />
</template>

<script>
import { data, textInFlags } from "@/data.js";
import Flags from "@/components/Flags.vue";

export default {
  name: "App",
  components: {
    Flags,
  },

  data() {
    return {
      risks: data, //imported from data.js
      count: '',
    };
  },
  methods: {
    //
    /// check count of checked inputs
    //
    check() {
      let count = 0;
      const checkbox = this.$refs.checkbox;
      checkbox.forEach((checkbox) => {
        if (checkbox.checked) count++ 
        this.count = count;
      });
      console.log(this.count);
    },
    //
    ///change color if risk conditions are met
    //
    changeColor() {
      const scamFor = this.$refs.scamFor;
      if (this.count == 0) return scamFor.style.backgroundColor = "green";
      if (this.count < 3) return scamFor.style.backgroundColor = "yellow";
      if (this.count < 5) return scamFor.style.backgroundColor = "orange";
      if(this.count >=5) return scamFor.style.backgroundColor = "red";
    },
    //
    /// change text in scamFor...textInFlags from data.js
    //
    changeText(){
      if (this.count == 0) return textInFlags[0];
      if (this.count < 3) return textInFlags[1];
      if (this.count < 5) return textInFlags[2];
      if(this.count >=5) return textInFlags[3];
    }
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
  display: flex;
  flex-direction: column;
  align-items: center;
  margin: 0.625rem;
}

#checkbox {
  margin: 0.5rem;
}
.risk {
  display: flex;
  align-items: center;
}
.scamFor {
  width: 100px;
  height: 100px;
  background: green;
  box-shadow: 1px 1px 5px rgba(17, 17, 17, 0.5);
  border-radius: 50%;

  display: flex;
  justify-content: center;
  align-items: center;
  font-size: 1.1rem;
}

#checkbox {
  -webkit-appearance: none;
  -moz-appearance: none;
  -ms-appearance: none;
  -o-appearance: none;
  appearance: none;
  height: 20px;
  width: 20px;
  transition: all 0.15s ease-out 0s;
  background: #cbd1d8;
  border: none;
  color: #fff;
  cursor: pointer;
  display: inline-block;
  margin-right: 0.5rem;
  outline: none;
  position: relative;
  z-index: 1000;
  border-radius: 100px;
}
#checkbox:hover {
  background: #9faab7;
}
#checkbox:checked {
  background: #40e0d0;
}
#checkbox:checked::before {
  height: 20px;
  width: 20px;
  position: absolute;
  content: "✔";
  display: inline-block;
  font-size: 0.9rem;
  text-align: center;
  border-radius: 50%;
}

</style>
