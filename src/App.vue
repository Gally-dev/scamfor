<template>
    <ul class="list">
      <li v-for="(risk, index) in risks" :key="risk.id" class="risk">
          <input
            type="checkbox"
            name="risk"
            id="checkbox"
            @click="check(risk, index, $event); changeColor()"
          />
          <label for="risk"> {{ risk }}</label>
      </li>
    </ul>
    <div class="scamFor" ref="scamFor"></div>
</template>

<script>
import { data } from "@/data.js";

export default {
  name: "App",
  components: {
    // List,
  },
  data() {
    return {
      risks: data, //imported from data.js
      checked: [],
    };
  },
  methods: {
    // count of checked checkboxes
    check(risk, index, $event) {
      if ($event.target.checked === true) {
        this.checked.push({
          id: index,
          risk: risk,
        });
      } else {
        this.checked = this.checked.filter((item) => item.id !== index);
      }
      // console.log(this.checked.sort((a,b) => (a.id - b.id))); //sorted as in the risk array
    },

    //change color if risk conditions are met
    changeColor(){
      let checkedRisks = this.checked.length

      if(checkedRisks == 0){
        this.$refs.scamFor.style.backgroundColor = "green"
      }else if(checkedRisks <= 3){
        this.$refs.scamFor.style.backgroundColor = "yellow"
      }else if(checkedRisks <= 5){
        this.$refs.scamFor.style.backgroundColor = "orange"
      }else{
        this.$refs.scamFor.style.backgroundColor = "red"
      }
    },
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
  align-items: center;
  margin: 0.625rem ;
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
  border-radius: 50%;
}
@keyframes click-wave {
  0% {
    height: 40px;
    width: 40px;
    opacity: 0.35;
    position: relative;
    border-radius: 50%;
  }
  100% {
    height: 40px;
    width: 40px;
    opacity: 0;
    border-radius: 50%;
  }
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
  /* line-height: 20px; */
  border-radius: 50%;
}
#checkbox:checked::after {
  -webkit-animation: click-wave 0.65s;
  -moz-animation: click-wave 0.65s;
  animation: click-wave 0.65s;
  background: #40e0d0;
  content: "";
}
</style>
