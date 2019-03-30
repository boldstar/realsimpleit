<template>
  <Layout>
    <div class="services-view">
      <Sidebar />
      <div class="selected">
        <h1>Services</h1>
        <p>Lorem ipsum dolor sit amet, consectetur adipisicing elit. Error doloremque omnis animi, eligendi magni a voluptatum, vitae, consequuntur rerum illum odit fugit assumenda rem dolores inventore iste reprehenderit maxime! Iusto.</p>
      </div>
    </div>
  </Layout>
</template>

<script>
import Sidebar from '@/components/Sidebar.vue'
export default {
  metaInfo: {
    title: 'Services'
  },
  components: {
    Sidebar
  }
}
</script>

<style>
  .services-view {
    display: flex;
    min-height: 100vh;
  }

  h1 {
    margin-top: 0;
  }

  .selected {
    width: 75%;
  }
</style>

