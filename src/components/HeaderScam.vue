<template>
  <header class="navbar">
    <div class="navbar-container">
     
      <div class="logo-wrap">
        <a href="https://blockchainslovakia.sk/">
          <img src="../../public/img/logo.svg" alt="logo">
          <img src="../../public/img/blockchain.svg" alt="logo-text">
        </a> 
      </div>
     
      <h1 class="navbar-item">SCAMAFÓR je nezávislá iniciatíva <br> O.z. Blockchain Slovakia</h1>
      
    </div>
  </header>
</template>

<script>
    export default {
        
    }
</script>

<style lang="css" scoped>
.navbar{
  width: 100%;
  height: 93px;
  background: #191642;

  display: flex;
 align-items:center;

}
.navbar-container{
  width: 1150px;
  margin: 0 auto;
  padding: 1rem;

  display: flex;
  justify-content: space-between;
  align-items: center;
}
.logo-wrap a{
  display: flex;
}
.logo-wrap :first-child{
margin-right: 10px;
}
.navbar-item{
  font-size:0.75rem ;
  font-weight: 500;
  line-height: 18px;
  letter-spacing: 0.02em;
  text-align: right;
  color: #ABBCE9;
}
/* media queries */
@media only screen and (max-width: 500px){
  .logo-wrap{
    width: 145px;
  }
  .navbar-item{
    font-size: 10px;
    line-height: 14px;
    letter-spacing: 2%;

  }
}

</style>