<template>
    <div class="sidebar" :class="{'sidebar-collapsed': toggle}">
      <button class="sidebar-btn" type="button" @click="toggleSidebar">
        <i class="material-icons btn-icon">
          menu
        </i>
      </button>
      <div class="service-list" :class="{'show-links': toggle}">
        <span class="service-category">Consulting</span>
        <hr>
        <ul>
          <li v-for="service in $static.services.edges" :key="service.id" @click="toggle = false">
            <g-link v-if="service.node.category == 'Consulting'" class="services-link" :to="service.node.path" :class="{'active-link' : service.node.path == $route.path}">{{ service.node.title }}</g-link>
          </li>
        </ul>
      </div>
      <div class="service-list" :class="{'show-links': toggle}">
        <span class="service-category">Managed</span>
        <hr>
        <ul>
          <li v-for="service in $static.services.edges" :key="service.id" @click="toggle = false">
            <g-link v-if="service.node.category == 'Managed'" class="services-link" :to="service.node.path" :class="{'active-link' : service.node.path == $route.path}">{{ service.node.title }}</g-link>
          </li>
        </ul>
      </div>
      <g-image src="../assets/img/microchip.png" class="microchip"></g-image>
    </div>
</template>

<static-query>
  query Services {
    services: allPost {
      edges {
        node {
          id
          title
          category
          path
        }
      }
    }
  }
</static-query>

<script>
export default {
    name: 'Sidebar',
    data() {
      return {
        toggle: false
      }
    },
    methods: {
      toggleSidebar() {
        this.toggle = !this.toggle
      }
    }
}
</script>

<style>
  .sidebar {
    width: 300px;
    display: flex;
    flex-direction: column;
    align-items: flex-start;
    border-right: 1px solid var(--main);
    background-color: rgb(245, 245, 245);
    padding: 10px;
  }

  .microchip {
    width: 100px;
    margin: 0 auto;
  }

  .sidebar-btn {
    display: none;
  }

  ul {
    list-style: none;
    text-align: right;
    padding-left: 0;
    padding-right: 30px;
  }

  .title {
    font-size: 1.3rem;
    font-weight: bold;
    background: none;
    border: none;
    cursor: pointer;
  }

  li {
    margin-bottom: 5px;
    padding-left: 15px;
    width: 100%;
  }

  .title:focus {
    outline: none;
  }

  .services-link {
    text-decoration: none;
    color: var(--gray);
    font-weight: bold;
  }

  .active-link {
    color: var(--main);
  }

  .service-category {
    font-weight: bold;
    font-size: 1.2rem;
  }

@media screen and (max-width: 767px) {
  .services-link {
    font-size: .8rem;
  }

  .microchip {
    display: none;
  }

  .title {
    font-size: 1rem;
  }

  .sidebar {
    width: 20px;
  }

  .service-list {
    display: none;
  }

  .sidebar-btn {
    display: block!important;
    background: none;
    border: none;
    cursor: pointer!important;
    z-index: 2;
    padding: 0;
  }

  .btn-icon {
    display: block!important;
    font-size: 1.4rem!important;    
    align-self: center;
    margin-top: 0!important;
    cursor: pointer!important;
    color: var(--main);
  }

  .sidebar-collapsed {
    width: 300px!important;
  }

  .show-links {
    display: flex;
    flex-direction: column;
  }
}
</style>
