<template>
    <header class="header" id="navbar">
      <div class="navbar">
        <strong>
          <g-link to="/"><g-image src="../assets/img/Logo.png" width="70" class="logo"></g-image></g-link>
        </strong>
        <nav class="nav">
          <g-link class="nav__link" to="/about">About Us</g-link>
          <i class="material-icons">description</i>
          <g-link class="nav__link" to="/service/free-network-assessment">Services</g-link>
          <i class="material-icons">dns</i>
          <a class="nav__link" href="#contact">Contact</a>
          <i class="material-icons">phone_in_talk</i>
          <a class="nav__link" href="#">Support</a>
          <i class="material-icons">launch</i>
        </nav>
      </div>
    </header>
</template>

<script>
export default {
    name: 'Navbar',
      methods:{
      handleSCroll (event) {
        let header = document.querySelector("#navbar");
        if (window.scrollY > 100 && !header.className.includes('navbar-sticky')) {
        header.classList.add('navbar-sticky'); 
        } else if (window.scrollY < 100) {
          header.classList.remove('navbar-sticky');
        }
      }
    },
    created() {
        window.addEventListener('scroll', this.handleSCroll);
    },
    destroyed () {
        window.removeEventListener('scroll', this.handleSCroll);
      } 
}
</script>

<style>
.header {
  margin-bottom: 20px;
  height: 70px;
}

.navbar {
  max-width: 1120px;
  justify-content: space-between;
  width: 100%;
  display: flex;
  margin: 0 auto;
  margin-top: 5px;
}

.nav {
    display: flex;
    align-self: center;
}

.nav__link {
  margin-left: 30px;
  text-decoration: none;
  font-size: 1.1rem;
  font-weight: bold;
  color: rgb(80, 80, 80);
  margin-right: 5px;
  letter-spacing: 2px;
}

.material-icons { 
    font-size: 1.1rem!important; 
    margin-top: 5px;
    color: var(--main);
}

.logo {
  margin-left: 10px;
  padding: 10px;
}

.navbar-sticky {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  background-color: var(--white);
  z-index: 1;
  box-shadow: 0 1px 10px rgba(0,0,0,250);
}
</style>
