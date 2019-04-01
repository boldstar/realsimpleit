<template>
  <Layout>
    <div class="about">
      <div class="about-us">
      <h1 class="about-header">About us</h1>
      <p class="p-details">Real.Simple.IT organized in January 2019 with the real simple goal of building a first rate company that partners with our customers to deliver  outstanding service in a consistent and cost effective way. We understand the complexity of building and maintaining your IT infrastructure and we believe in proactive IT management by maximizing the benefits of technology with daily, weekly and monthly automated IT tasks that ensure all jobs are completed consistently and without fail. We strive to provide our customers with reliability, security and performance by using our identified “best practices” developed over years of collective experience. Real.Simple.IT knows that consistency creates reliability which results in predictable costs. Our goal is to serve as your technology partner using a consultative approach to evaluate your business and help you untangle your current and future IT needs.</p>
      </div>
      <div class="management">
        <h1 class="about-header">Management</h1>
        <p class="p-details">Trey Caples, President/Engineering Principal – Trey brings over 20 years of experience in IT management and consulting services to Real.Simple.IT and holds numerous certifications as well as being a RSA certified security professional.  Before starting Real.Simple.IT, he worked for companies large and small as a consultant and as a full time IT Director. Through hard work and hard won experience, he learned how to keep critical networks running smoothly and helped achieve the greatest returns on a company’s IT investments.</p>
      </div>
    </div>
  </Layout>
</template>

<script>
export default {
  metaInfo: {
    title: 'About us'
  }
}
</script>

<style>
  .about {
    max-height: 100vh;
    margin-bottom: 100px;
    padding: 20px;
  }

  .p-details {
    font-size: 1.15rem;
  }

  @media screen and (max-width: 767px) {
    .p-details {
      font-size: .9rem;
    }

    .about-header {
      font-size: 1.15rem;
    }

    .about {
      padding: 0 20px;
    }
  }
</style>

