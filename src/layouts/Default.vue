<template>
  <div class="layout">
    <div class="layout-container">
      <Navbar id="navbar" />
      <!-- content -->
      <transition name="fade" appear>
        <main>
          <slot/>
        </main>
      </transition>
    </div>
    <Partners />
    <Contact />
    <Footer />
  </div>
</template>

<static-query>
query {
  metaData {
    siteName
  }
}
</static-query>

<script>
import Navbar from '@/components/Navbar.vue'
import Contact from '@/components/Contact.vue'
import Footer from '@/components/Footer.vue'
import Partners from '@/components/Partners.vue'
export default {
  name: 'layout',
  components: {
    Navbar,
    Contact,
    Footer,
    Partners
  },
}
</script>


<style>
@import url('https://fonts.googleapis.com/css?family=Montserrat');


:root {
  --main: rgb(0,207,255);
  --gray: rgb(112,112,112);
  --white: rgb(255,255,255);
}


body {
  font-family: 'Montserrat', sans-serif ,Arial,sans-serif;
  margin:0;
  padding:0;
  line-height: 1.5;
}

.layout {
  margin: 0 auto;
}

.layout-container {
  max-width: 1120px;
  margin: 0 auto;
}

.fade-enter-active {
  transition: opacity 1.5s;
}

.fade-enter {
  opacity: 0;
}
</style>
