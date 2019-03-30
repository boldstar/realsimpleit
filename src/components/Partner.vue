<template>
  <div class="partner">
    <i class="material-icons">{{icon}}</i>
    <span class="title">{{title}}</span>
  </div>
</template>

<script>

export default {
    name: 'Partner',
    props: ['icon', 'title']

}
</script>

<style scoped>
  .partner {
    display: flex;
    flex-direction: column;
    align-items: center;
    width: 250px;
  }

  .title {
    font-size: 1.1rem;
    font-weight: bold;
  }

  .material-icons {
    font-size: 5rem!important;
  }
</style>
