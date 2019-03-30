<template>
    <header class="header">
      <strong>
        <g-link to="/"><g-image src="../assets/img/Logo.png" width="70" class="logo"></g-image></g-link>
      </strong>
      <nav class="nav">
        <g-link class="nav__link" to="/about">About Us</g-link>
        <i class="material-icons">description</i>
        <g-link class="nav__link" to="/services">Services</g-link>
        <i class="material-icons">dns</i>
        <a class="nav__link" href="#contact">Contact</a>
        <i class="material-icons">phone_in_talk</i>
        <a class="nav__link" href="#">Support</a>
        <i class="material-icons">launch</i>
      </nav>
    </header>
</template>

<script>
export default {
    name: 'Navbar'
}
</script>

<style>
.header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin-bottom: 20px;
  height: 70px;
}

.nav {
    display: flex;
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
</style>
