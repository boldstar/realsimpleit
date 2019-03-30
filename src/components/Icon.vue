<template>
  <div class="icon">
    <i class="material-icons">{{icon}}</i>
    <span class="title">{{title}}</span>
  </div>
</template>

<script>

export default {
    name: 'Icon',
    props: ['icon', 'title']
}
</script>

<style scoped>
  .icon {
    display: flex;
    flex-direction: column;
    align-items: center;
    height: 150px;
    width: 300px;
    box-shadow: 0 2px 15px 8px rgba(0, 0, 0, 0.164); 
    border-radius: 8px;
  }

  .title {
    font-size: 1.1rem;
    font-weight: bold;
  }

  .material-icons {
    font-size: 5rem!important;
  }
</style>
