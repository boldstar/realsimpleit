<template>
  <div class="partners">
    <h2 class="partners-header">Partnerships</h2>
    <div class="partners-background">
      <div class="partners-content">
        <img src="../../static/assets/cisco_logo.png" alt="cisco" class="partner-img">
        <img src="../../static/assets/vmware_logo.png" alt="vmware" class="partner-img">
        <img src="../../static/assets/microsoft_logo.png" alt="microsoft" class="partner-img">
        <img src="../../static/assets/dellemc_logo.jpg" alt="dellemc" class="partner-img">
        <img src="../../static/assets/aws_logo.png" alt="aws" class="partner-img">
        <img src="../../static/assets/veeam_logo.jpg" alt="veeam" class="partner-img">
        <img src="../../static/assets/acronis_logo.png" alt="acronis" class="partner-wide-img">
        <img src="../../static/assets/ingram_logo.png" alt="ingram" class="partner-wide-img">
        <img src="../../static/assets/watchguard_logo.png" alt="watchguard" class="partner-wide-img">
      </div>
    </div>
  </div>
</template>

<script>

export default {
    name: 'Partners',
}
</script>

<style>
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
  .partner-wide-img {
    width: 400px;
    height: 100px;
    margin: 20px;
    align-self: center;
    background-color: white;
    border-radius: 15px;
  }
  @media screen and (max-width: 550px) {
    .partner-wide-img {
      width: 300px;
      height: 70px;
    }
  }
</style>
