<template>
    <div class="sidebar">
      <div class="service-list">
        <span class="service-category">Consulting</span>
        <hr>
        <ul>
          <li v-for="service in $static.services.edges" :key="service.id">
            <g-link v-if="service.node.category == 'Consulting'" class="services-link" :to="service.node.path" :class="{'active-link' : service.node.path == $route.path}">{{ service.node.title }}</g-link>
          </li>
        </ul>
      </div>
      <div class="service-list">
        <span class="service-category">Managed</span>
        <hr>
        <ul>
          <li v-for="service in $static.services.edges" :key="service.id">
            <g-link v-if="service.node.category == 'Managed'" class="services-link" :to="service.node.path" :class="{'active-link' : service.node.path == $route.path}">{{ service.node.title }}</g-link>
          </li>
        </ul>
      </div>
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
        managed: false,
        consulting: false,
      }
    },
    methods: {
      showManaged() {
        this.managed = !this.managed
      },
      showConsulting() {
        this.consulting = !this.consulting
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
    border-right: 1px solid black;
    background-color: rgb(235, 235, 235);
    padding: 10px;
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
</style>
