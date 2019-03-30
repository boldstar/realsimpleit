<template>
  <div class="contact">
      <div class="contact-details">
        <h2>Learn More</h2>
        <p>To learn more about our services or if you have any questions please feel free to call us at (111) 222-3333 or fill out the form on the right. Looking forward to hearing from you!</p>
        <g-image src="../assets/img/Arrow.png" width="250" class="arrow"></g-image>
      </div>
      <Form :slogan="'Get your free quote today!'" id="contact" />
  </div>
</template>

<script>
import Form from '@/components/Form.vue'
export default {
    name: 'Contact',
    components: {
      Form
    }
}
</script>

<style>
  .contact {
    display: flex;
    justify-content: space-around;
    margin-bottom: 50px;
  }

  .contact-details {
    width: 400px;
  }

  @media screen and (max-width: 1000px) {
    .contact-details {
      display: none;
    }

    .arrow {
      display: none;
    }
  }
</style>
