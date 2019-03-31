<template>
  <Layout>
    <section class="hero">
      <g-image src="../assets/img/HeroBackground.png" class="hero-background"></g-image>
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
      <Form :slogan="'Get your free assessment today!'" class="form" />
    </section>
    <section class="services">
      <h2 class="services-header">Our Services</h2>
      <div class="services-content">
        <div class="services-section">
          <h2>Managed Services</h2>
          <div class="service-icons">
            <Icon :icon="'dns'" :title="'Infrastructure Solutions'" />
            <Icon :icon="'cast_connected'" :title="'Systems Integration'" />
            <Icon :icon="'security'" :title="'Network Security'" />
          </div>
        </div>
        <div class="services-section">
          <h2>Consulting Services</h2>
          <div class="service-icons">
            <Icon :icon="'storage'" :title="'System Log Monitoring'" />
            <Icon :icon="'developer_board'" :title="'Daily System Audits'" />
            <Icon :icon="'wifi_lock'" :title="'Virus Protection Management'" />
          </div>
        </div>
      </div>
      <g-link to="/service/free-network-assessment" class="service-link">Learn More>></g-link>
    </section>
  </Layout>
</template>

<script>
import Form from '@/components/Form.vue'
import Icon from '@/components/Icon.vue'
export default {
  metaInfo: {
    title: 'Hello, world!'
  },
  components: {
    Form,
    Icon
  }
}
</script>

<style>
.home-links a {
  margin-right: 1rem;
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

.services {
  display: flex;
  flex-direction: column;
  align-items: center;
  position: relative;
  margin-bottom: 50px;
}

.services-content {
  display: flex;
  flex-direction: column;
  align-items: flex-start;
  width: 100%;
  margin-top: 25px;
}


.services-header {
  font-size: 2.0rem;
  margin-top: 0;
  color: var(--white);
}

.services-section {
  display: flex;
  flex-direction: column;
  width: 100%;
}

.service-icons {
  display: flex;
  justify-content: space-between;
  width: 100%;
}

.service-link {
  text-decoration: none;
  color: var(--gray);
  font-size: 1.2rem;
  font-weight: bold;
  border-bottom: 2px solid var(--main);
  align-self: flex-end;
  margin-top: 25px;
  margin-bottom: 5px;
}

.service-link:hover {
  color: black;
}
</style>
