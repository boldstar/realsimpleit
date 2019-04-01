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
    justify-content: center;
  }

  .title {
    font-size: 1.1rem;
    font-weight: bold;
  }

  .material-icons {
    font-size: 5rem!important;
    color: var(--main);
  }

  @media screen and (max-width: 1120px) {
    .icon {
      height: 100px;
      width: 200px;
    }

    .material-icons {
      font-size: 2.5rem!important;
    }

    .title {
      font-size: .7rem;
      font-weight: lighter;
    }
  }

  @media screen and (max-width: 767px) {
    .icon {
      margin: 10px auto;
      width: 100%;
    }

    .material-icons {
      font-size: 3.5rem!important;
    }

    .title {
      font-size: 1.0rem;
      font-weight: bold;
    }
  }
</style>
