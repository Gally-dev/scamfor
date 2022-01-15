<template>
    <section class="inputs">
        <div class="inputs-wrapper">
            <div class="scamFor" ref="scamFor">
                <p class="risk-options">{{ changeText() }}</p>
                <p class="count" v-if="count > 0">{{count}}</p> 
            </div>

            <div class="list-wrap">
                <h2>Zoznam rizikových faktorov <img src="../../public/img/flag.svg" alt="flag"> </h2>
                <ul class="list">

                    <li i v-for="risk in risks" :key="risk.id" class="risk">
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
            </div>


        </div>
    </section>
</template>

<script>
    import { data, textInFlags } from "@/data.js";

    export default {
  name: "App",
  components: {
    
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
      if (this.count == 0) return scamFor.style.backgroundColor = "#20D267";
      if (this.count < 3) return scamFor.style.backgroundColor = "#FFCD1B";
      if (this.count < 5) return scamFor.style.backgroundColor = "#FF833E";
      if(this.count >=5) return scamFor.style.backgroundColor = "#FF002E";
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

<style lang="css" scoped>

/* left side */
.inputs{
    background: #fff;
}
.inputs-wrapper{
    width: 60%; /*968px*/
    margin: 0 auto;
    padding-top: 84px;

    display: flex;
    justify-content: space-between;
}
.scamFor{
  width: 170px;
  height: 170px;
  border-radius: 50%;
  background: #20D267;
  position: sticky;
  top: 20px;
  margin-top: 82px;
}
.risk-options{
  color: #191642;
  font-size: 1.25rem; /*20px*/
  font-weight: 500;
  line-height: 1.875rem; /*30px*/
  text-align: center;
  
  position: absolute;
  bottom: -65px;
  }
  .count{
    text-align: center;
    font-size: 30px;
    font-weight: 700;
    color: #ffff;
    position: absolute;
    top: 50%;
    right: 50%;
    transform: translate(50%, -50%);
  }
  .list-wrap{
    width: 560px;

  }
.list{
  list-style: none;
}
label{
  font-size: 18px;
  line-height: 28px;
  color: #191642;
  display: block;
  max-width: 516px;
}

/* right side */
.list-wrap h2{
  color: #191642;
  font-size: 20px;
  font-weight: 600;
  line-height: 30px;
  margin-bottom: 40px;
}
  .risk{
    display: inline-flex;
    /* justify-content: space-between; */
    align-items: flex-start;
    margin-bottom: 40px;
  }
input#checkbox{
  position: relative;
  width: 22px;
  height: 22px;
  margin-top: 10px;
  -webkit-appearance: none;
  appearance: none;
  border: 1px solid #AFAFC1;
  border-radius: 2px;
  margin-right:22px;
}

#checkbox:checked::before {
  height: 20px;
  width: 20px;
  position: absolute;
  content: url(../../public/img/check.svg);
  display: inline-block;
  font-size: 1.1rem;
  text-align: center;
  color: #fff;
  background: #3c3cdd;
  border-radius: 1px;
}

/* Warning */



/* old css */
/* #checkbox {
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
} */
</style>