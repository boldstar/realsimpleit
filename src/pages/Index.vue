<template>
  <Layout>
    <div class="index">
      <g-image src="../assets/img/HeroBackground.png" class="hero-background"></g-image>
      <div class="hero">
        <div class="hero-details">
          <h1 class="hero-header">Real.Simple.IT</h1>
          <p class="hero-info">At Real.Simple.IT, our goal is to bring high quality managed services to you and your business. We understand the importance of security and performance of your technology infrastructure. </p>
          <p class="hero-call-to-action">Apply for a free assessment today to learn more about what we have to offer!</p>
          <g-image src="../assets/img/Arrow.png" width="250" class="arrow"></g-image>
          <div class="btn-group">
            <g-link class="services-btn" to="/services">Services</g-link>
            <a class="contact-btn" href="#contact">Free Assesment</a>
          </div>
        </div>
        <Form :slogan="'Get your free assesment today!'" class="form" />
      </div>
    </div>
  </Layout>
</template>

<script>
import Form from '@/components/Form.vue'
export default {
  metaInfo: {
    title: 'Hello, world!'
  },
  components: {
    Form
  }
}
</script>

<style>
.home-links a {
  margin-right: 1rem;
}

.index {
  min-height: 100vh;
}

.hero {
  display: flex;
  justify-content: space-around;
  align-items: center;
  height: calc(100vh - 150px);
}

.hero-details {
  width: 500px;
  margin-bottom: 20px;
}

.hero-background {
  position: absolute;
  top: 0;
  left: 0;
  z-index: -100;
  width: 100%;
  max-height: 100vh;
  min-height: 100vh;
}

.hero-header {
  color: var(--main);
}

.hero-info {
  font-size: 1.25rem;
}

.hero-call-to-action {
  font-size: 1.25rem;
  font-weight: bold;
}

.arrow {
  position: relative;
  left: 200px;
}

.btn-group {
  display: none;
}

.services-btn {
  background: var(--white);
  color: var(--gray);
  font-size: 1.1rem;
  padding: 10px;
  border-radius: 3px;
  border: none;
  margin-right: 25px;
  text-decoration: none;
  cursor: pointer;
}

.contact-btn {
  background: var(--gray);
  color: var(--main);
  font-size: 1.1rem;
  padding: 10px;
  border-radius: 3px;
  border: none;
  text-decoration: none;
  font-weight: bold;
  cursor: pointer;
}

@media screen and (max-width: 1000px) {
  .form {
    display: none;
  }

  .arrow {
    display: none;
  }

  .btn-group {
    display: block;
  }
}
</style>
