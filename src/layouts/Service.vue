<template>
  <div class="layout">
    <div class="layout-container">
      <Navbar />
      <!-- content -->
      <div class="service-content">
        <Sidebar />
        <transition name="fade" appear>
          <main>
            <slot/>
          </main>
        </transition>
      </div>
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
import Sidebar from '@/components/Sidebar.vue'
export default {
  name: 'service-layout',
  components: {
    Navbar,
    Contact,
    Footer,
    Partners,
    Sidebar
  },
}
</script>


<style>
@import url('https://fonts.googleapis.com/css?family=Montserrat');
@import url('https://cdnjs.cloudflare.com/ajax/libs/github-markdown-css/3.0.1/github-markdown.min.css');


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

.service-content {
  display: flex;
  min-height: 80vh;
}

.markdown-body {
		box-sizing: border-box;
		min-width: 200px;
		max-width: 980px;
		margin: 0 auto;
		padding: 0 45px;
    font-weight: bold;
	}

	@media (max-width: 767px) {
		.markdown-body {
			padding: 15px;
      font-size: .8rem;
		}
	}
</style>
