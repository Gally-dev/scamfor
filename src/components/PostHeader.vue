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
    background:#F6F6FC;

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

/* media queries */
@media only screen and (max-width: 1024px) {
  .post-header-wrap {
    flex-direction: column-reverse;
  }
  .post-header-colors{
      margin-bottom: 20px;
  }
  @media only screen and (max-width: 768px){
      .flags{
    width: 90px;
    height: 90px;
    }
  }
  @media only screen and (max-width: 500px){
      .flags{
          width: 40px;
          height: 40px;
          margin-right: 5px;
      }
      .post-header-text h1{
          font-size: 2.75rem; /*44px */
          line-height: 54px;
      }
      .post-header p{
          font-size: 20px;
          line-height: 30px;
      }
      .post-header-colors p{
          font-size: 1rem;
      }
  }
}
</style>
