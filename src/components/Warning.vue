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
        margin: 44px auto 84px auto;
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
    /* media queries */
    @media only screen and (max-width: 768px){
        .warning-wrap{
            flex-direction: column;
            align-items: center;
            width: 100%;
            padding: 1rem;
        }
        .warning-wrap img{
            width: 48px;
            height: 48px;
        }
        .warning-wrap p{
            margin: 0;
            text-align: center;
        }
    }

    @media only screen and (max-width: 620px){
         .warning{
            width: 93%;
            height: 224px;
            /* padding:1rem; */
            margin-top: 5px;
            margin-bottom: 44px;
    
        }
        
        .warning-wrap img{
            margin: 0.5rem;
        }
    }
    
</style>
