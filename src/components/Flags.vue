<template>
  <section class="trafficLights">
    <div class="circle">
      <p>0</p>
    </div>
    <div class="circle">
      <p>&#60; 3</p>
    </div>
    <div class="circle">
      <p>&#60; 5</p>
    </div>
    <div class="circle">
      <p>5 a viac</p>
    </div>
  </section>
</template>

<script>
export default {};
</script>

<style lang="css" scoped>
.trafficLights {
  display: flex;
}
.circle {
  width: 80px;
  height: 80px;
  border-radius: 50%;
  margin: 10px;
  box-shadow: 1px 1px 5px rgba(17, 17, 17, 0.5);
 
  display: flex;
  justify-content: center;
  align-items: center;
}
.circle p{
    font-size: 1.2rem;
    font-weight: 400;
}
.circle:nth-child(1) {
  background: green;
}
.circle:nth-child(2) {
  background: yellow;
}
.circle:nth-child(3) {
  background: orange;
}
.circle:nth-child(4) {
  background: red;
}
</style>
