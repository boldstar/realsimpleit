<template>
  <div class="modal">
    <div class="modal-content">
      <div class="modal-details">
        <span class="text">Thanks, for your interest</span>
        <br>
        <br>
        <span class="text">We will be in touch soon!</span>
        <br>
        <br>
        <small>If you do not here from us, please give us a call at<br/> 832-879-0478</small>
      </div>
      <div class="buttons">
        <button type="button" class="modal-btn" @click="closeModal">Thanks!</button>
      </div>
    </div>
  </div>
</template>

<script>

export default {
    name: 'Modal',
    props: ['name'],
    methods: {
      closeModal() {
        this.$emit('close-modal')
      }
    }
}
</script>

<style scoped>
  .modal {
     background: rgba(0, 0, 0, 0.100);
     background-size: cover;
     height: 100vh;
     width: 100vw;
     z-index: 1000;
  }

  .modal-content {
    margin: 150px auto;
    width: 25%;
    height: 200px;
    background-color: white;
    border-radius: 10px;
    box-shadow: 0 2px 15px 8px rgba(0, 0, 0, 0.164);
    display: flex;
    flex-direction: column;
    align-items: center;
    padding: 10px;
  }

  .buttons {
    width: 100%;
  }

  .modal-details {
    height: 100%;
  }

  .modal-btn {
    width: 100%;
    height: 40px;
    border-radius: 8px;
    background-color: var(--main);
    border: none;
    font-size: 1.2rem;
    color: white;
    cursor: pointer;
  }

  .text {
    font-size: 1rem;
    margin: auto;
  }

  @media screen and (max-width: 767px) {
    .modal-content {
      width: 75%;
    }
  }

  @media screen and (max-width: 400px) {
    .modal-btn {
      height: 30px;
      font-size: 1rem;
    }

    .text {
      font-size: .8rem;
    }
  }
</style>
