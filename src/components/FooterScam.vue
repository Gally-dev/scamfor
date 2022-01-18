<template>
  <footer class="footer">
    <div class="footer-wrap">
      <p>Všetký práva vyhradené © 2022 | Blockchain Sloavakia O.z.</p>
      <a href="https://blockchainslovakia.sk/" target="_blank" rel="noopener noreferrer">blockchainslovakia.sk</a
      >
    </div>
  </footer>
</template>

<script>
export default {};
</script>

<style lang="css" scoped>
.footer {
  width: 100%; /*1600px*/
  height: 50px;
  margin: 0 auto;
  background: #f6f6fc;
  color: #7e7e9c;

  display: flex;
  justify-content: center;
  align-items: center;
}
.footer-wrap {
  width: 1170px;
  padding: 16px;

  display: flex;
  justify-content: space-between;
  align-items: center;
}
.footer a {
  color: #7e7e9c;
}
@media only screen and (max-width: 660px) {
  .footer {
    height: 92px;
  }
  .footer-wrap {
    align-items: flex-start;
    flex-direction: column;
    font-size: 0.75rem; /*12px */
    line-height: 18px;
  }
}
@media only screen and (max-width: 620px) {
  .footer {
    align-items: flex-start;
    height: 138px;
  }
}
</style>
