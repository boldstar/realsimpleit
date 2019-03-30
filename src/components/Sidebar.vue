<template>
    <div class="sidebar">
      <button type="button" class="title" @click="showManaged">Managed</button>
      <ul v-if="managed">
        <li>Service 1</li>
        <li>Service 2</li>
        <li>Service 3</li>
      </ul>
      <button type="button" class="title" @click="showConsulting">Consulting</button>
      <ul v-if="consulting">
        <li>Service 1</li>
        <li>Service 2</li>
        <li>Service 3</li>
      </ul>
    </div>
</template>

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
  }

  .title:focus {
    outline: none;
  }
</style>
