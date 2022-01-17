<template>
  <section class="warning">
    <div class="warning-wrap">
      <img src="../../public/img/warning.svg" alt="warning" />
      <p>
        Scamafór má byť len pomocným nástrojom a jeho účelom nie je nahradiť
        obozretné preverenie investičného produktu alebo poskytovateľa služieb
        súvisiacich s kryptoaktívami. Na ceste k investovaniu nie je opatrnosti
        nikdy dosť!
      </p>
    </div>
  </section>
</template>

<script>
export default {};
</script>

<style lang="css" scoped>
    .warning{
        width: 68%; /*970px*/
        
        border: 1px solid #E7E7F1;
        border-radius: 5px;
        margin: 0 auto;
        height: 172px;

        display: flex;
        justify-content: center;
        align-items: center;
    }
    .warning-wrap{
        width: 67%; /*656px*/
        /* width: 656px; */
        position: relative;
        /* left: 214px; */
        display: flex;
       
    }
    .warning-wrap p{
        color: #7E7E9C;
        /* width: 100%; */

        font-size: 0.875rem;    /*14px */
        line-height: 1.5rem;    /*24px*/
        margin-left: 40px;
    }
</style>
