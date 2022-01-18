<template>
    <section class="inputs">
        <div class="inputs-wrapper">

          <div class="scamFor-wrapper">
            <div class="scamFor" ref="scamFor">
                <p class="risk-options">{{ changeText() }}</p>
                <p class="count" v-show="count > 0">{{count}}</p> 
            </div>
          </div>


            <div class="list-wrap">
                <h2>Zoznam rizikových faktorov <img src="../../public/img/flag.svg" alt="flag"> </h2>
                <ul class="list">
                    <li  v-for="risk in risks" :key="risk.id" class="risk">
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
  /* display: none; */
  width: 170px;
  height: 170px;
  border-radius: 50%;
  background: #20D267;
  /* position: fixed; */
  position: sticky;
  position: -webkit-sticky;
  top: 20px;
  
  margin-top: 82px;
}
.scamFor-mobile{
  display: none;
  display: block;
  position: absolute;
  width: 100%;
  height: 66px;
    background: red;
  position: fixed;
  z-index: 1;
  bottom: 0;
 
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
    /* width: 560px; */
    /* width: 60%; */
    width: 66%;

  }
.list{
  list-style: none;
}
label{
  font-size: 18px;
  line-height: 28px;
  color: #191642;
  display: block;
  /* width: 516px; */
  width: 100%;
  position: relative;
  top: -10px;
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
    align-items: flex-start;
    margin-bottom: 40px;
  }
input#checkbox{
  position: relative;
  width: 22px;
  height: 22px;
 
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

@media only screen and (max-width: 1024px) {
  .inputs-wrapper {
    width: 100%;
    justify-content: space-between;
    padding: 84px 16px 0 16px;
    }
    
  }
  @media only screen and (max-width: 768px) {
    .scamFor{
      width: 150px;
      height: 150px;
    }
    .risk{
      margin-bottom: 20px;
    }
  }

@media only screen and (max-width: 620px){
  
  .inputs-wrapper{
    display: block;
    padding-top: 44px;
    
  }
  .scamFor-wrapper{
    width: 100%;
    height: 66px;
    background: #ffffff;
    box-shadow: 0 0 10px rgba(17, 17, 17, 0.25);

    position: fixed;
    bottom: 0;
    left: 0;

    z-index: 2;
  }
  .scamFor{
    margin-top: 0;
    position: relative;
    top: 10.5px;
    left: 20px;
    width: 45px;
    height: 45px;
    
  }
  .risk-options{
    width: 230px;
    bottom: 7px;
    left:50px;
    font-size: 1.125rem; /*18px */
    line-height: 30px;
  }
  .count{
    font-size: 1rem;
  }
  .list-wrap{
    width: 100%;
  }
  .warning{
    width: 100%;
  }
}
@media only screen and (max-width: 500px){
  label{
    font-size:1rem ; /*16px*/
    line-height: 26px;
  }
}

</style>