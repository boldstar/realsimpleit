<template>
  <div class="contact">
      <h2 class="contact-header">Contact Us</h2>
      <div class="contact-content">
        <div class="contact-details">
          <h2>Learn More</h2>
          <p>To learn more about our services or if you have any questions please feel free to call us at (111) 222-3333 or fill out the form on the right. Looking forward to hearing from you!</p>
          <img src="../../static/assets/img/Arrow.png" width="250" class="arrow">
        </div>
        <Form :slogan="'Get your free quote today!'" id="contact" class="contact-form" />
      </div>
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
    flex-direction: column;
    align-items: center;
    background-image: url('../../static/assets/img/ContactBackground.png');
    background-color: var(--gray);
    background-position: center;
    background-size: cover;
    background-repeat: no-repeat;
    height: 100vh;
  }

  .contact-header {
    font-size: 2.0rem;
    margin-top: 50px;
    color: var(--main);
  }

  .contact-content {
    max-width: 1120px;
    display: flex;
    justify-content: space-around;
    align-self: center;
    width: 100%;
    margin-top: 75px;
  }

  .contact-details {
    width: 400px;
  }

  .contact-form {
    align-self: start;
  }

  @media screen and (max-width: 1000px) {
    .contact-details {
      display: none;
    }

    .arrow {
      display: none;
    }
  }

  @media screen and (max-width: 767px) {
    .contact-content {
      margin-top: 10px;
    }
  }
</style>
