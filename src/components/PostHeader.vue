<template>
  <section class="post-header">
      <div class="post-header-wrap">
        <div class="post-header-text">
            <h1>SCAM<span>AFÓR</span></h1>
            <p>Kliknite na rizikové faktory <br> a SCAMfór sa zmení farbou podľa rizika</p>
        </div>

        <div class="post-header-colors">
           <p class="flags">0</p>
           <p class="flags">&#60;3</p>
           <p class="flags">&#60;5</p>
           <p class="flags">5+</p>
        </div>

      </div>
  </section>
</template>

<script>
export default {};
</script>

<style lang="css" scoped>
.post-header{
    height: 354px;
    color:#F6F6FC;

    display: flex;
    align-items: center;
}
.post-header-wrap{
    width: 1150px;
    padding: 1rem;
    margin: 0 auto;

    display: flex;
    justify-content: space-between;
    
}
/* left side */

.post-header-text h1{
    font-weight: 700;
    font-size: 4rem;
    line-height: 4.625rem;
    color:#191642;
}
h1 span{
    color:#76739f;
}
.post-header-text p{
    color: #191642;
    font-size: 32px;
    line-height: 42px;
    font-weight: 500;
}
/* right side */
.post-header-colors{
    display: flex;
    align-items: flex-end;
}

.flags{
    width: 108px;
    height: 108px;
    border-radius: 50%;
    margin-right: 10px;

    color: #FFFFFF;
    font-size: 27px;
    font-weight: 700;
    display: flex;
    justify-content: center;
    align-items: center;
}
.flags:nth-child(1){background:#20D267;}
.flags:nth-child(2){background:#FFCD1B;}
.flags:nth-child(3){background:#FF833E;}
.flags:nth-child(4){background:#FF002E; margin: 0;}
</style>
