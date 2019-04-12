<template>
    <header class="header" id="navbar">
      <div class="navbar">
        <strong>
          <g-link to="/"><img src="../../static/assets/img/Logo.png" width="70" class="logo"></g-link>
        </strong>
        <div class="navbar-links">
          <div class="div-btn"> 
            <button class="nav-btn" type="button" @click="toggleNav">
              <i class="material-icons btn-icon">
                menu
              </i>
            </button>
          </div>
          <nav class="nav" :class="{'nav-collapsed' : toggle}">
            <g-link class="nav__link" to="/about" :class="{'active-g-link': $route.name == 'about'}">About Us</g-link>
            <i class="material-icons">description</i>
            <g-link class="nav__link" to="/service/free-network-assessment">Services</g-link>
            <i class="material-icons">dns</i>
            <a class="nav__link" href="#contact">Contact</a>
            <i class="material-icons">phone_in_talk</i>
            <a class="nav__link" href="https://na1vsa37.kaseya.net/dl.asp?id=22191582">Support</a>
            <i class="material-icons">launch</i>
          </nav>
        </div>
      </div>
    </header>
</template>

<script>
export default {
    name: 'Navbar',
      data() {
        return {
          toggle: false
        }
      },
      methods:{
      handleSCroll (event) {
        let header = document.querySelector("#navbar");
        if (window.scrollY > 100 && !header.className.includes('navbar-sticky')) {
        header.classList.add('navbar-sticky'); 
        } else if (window.scrollY < 100) {
          header.classList.remove('navbar-sticky');
        }
      },
      toggleNav() {
        this.toggle = !this.toggle
      }
    },
    mounted() {
        window.addEventListener('scroll', this.handleSCroll);
    },
}
</script>

<style scoped>
.header {
  margin-bottom: 20px;
  height: 70px;
  background: white!important;
  z-index: 2;
}

.navbar {
  max-width: 1120px;
  justify-content: space-between;
  width: 100%;
  display: flex;
  margin: 0 auto;
  margin-top: 5px;
}

.navbar-links {
  display: flex;
  flex-direction: column;
  align-self: center;
  background: var(--white);
  z-index: 2;
}

.nav {
    display: flex;
    align-self: center;
    margin-right: 30px;
    background: var(--white);
    z-index: 2;
}

.nav-btn {
  display: none;
  cursor: pointer;
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

.active-g-link {
  color: var(--main);
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

.nav-btn {
  display: none!important;
}

@media screen and (max-width: 767px) {
  .navbar {
    background: white!important;
    z-index: 2;
  }

  .nav {
    display: none;
  }

  .div-btn {
    margin-right: 25px;
  }

  .nav-collapsed {
    display: flex!important;
    flex-direction: column!important;
    align-items: flex-end;
    background: var(--white);
    overflow: auto;
  }

  .material-icons {
    display: none!important;
  }

  .nav__link {
    margin-bottom: 10px;
  }

  .nav-btn {
    display: block!important;
    background: none;
    border: none;
    cursor: pointer!important;
    z-index: 2;
    margin-left: auto;
    margin-bottom: 10px;
    margin-top: 10px;
  }

  .btn-icon {
    display: block!important;
    font-size: 2rem!important;    
    align-self: center;
    margin-top: 0!important;
    cursor: pointer!important;
  }

  .nav-btn:hover {
    color: black;
  }
}
</style>
