<template>
  <div class="partners">
    <h2 class="partners-header">Partnerships</h2>
    <div class="partners-background">
      <div class="partners-content">
        <img src="../../static/assets/img/cisco_logo.png" class="partner-img">
        <img src="../../static/assets/img/vmware_logo.png" class="partner-img">
        <img src="../../static/assets/img/microsoft_logo.png" class="partner-img">
        <img src="../../static/assets/img/dellemc_logo.jpg" class="partner-img">
        <img src="../../static/assets/img/aws_logo.png" class="partner-img">
        <img src="../../static/assets/img/veeam_logo.jpg" class="partner-img">
        <img src="../../static/assets/img/ingram_logo.png" class="watchguard-img">
        <img src="../../static/assets/img/watchguard_logo.png" class="watchguard-img">
        <img src="../../static/assets/img/acronis_logo.png" class="watchguard-img">
      </div>
    </div>
  </div>
</template>

<script>

export default {
    name: 'Partners'
}
</script>

<style scoped>
  .partners {
    display: flex;
    flex-direction: column;
    align-items: center;
  }

  .partners-header {
    font-size: 2.0rem;
    margin-top: 0;
    color: var(--main);
  }

  .partners-background {
    background-color: var(--gray);
    width: 100%;
  }

  .partners-content {
    width: 100%;
    max-width: 1120px;
    display: flex;
    justify-content: space-around;
    flex-wrap: wrap;
    padding: 50px 0;
    margin: 0 auto;
  }

  .partner-img {
    width: 200px;
    height: 150px;
    margin: 20px;
    align-self: center;
    border-radius: 15px;
    background-color: white;
  }

  .watchguard-img {
    width: 400px;
    height: 100px;
    margin: 20px;
    align-self: center;
    background-color: white;
    border-radius: 15px;
  }

  @media screen and (max-width: 550px) {
    .watchguard-img {
      width: 300px;
      height: 70px;
    }
  }
</style>
