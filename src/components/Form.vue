<template>
     <form action="/" name="Free Assessment Form" data-netlify="true" netlify-honeypot="bot-field" method="post">
      <span class="slogan">{{ slogan }}</span>
      <p class="hidden-input">
        <label>Don’t fill this out if you're human: <input name="bot-field" /></label>
      </p>
      <input v-model="formData.business_name" type="text" name="Business Name" placeholder="Business Name" :class="{'input-error': error}" @change="error = false">
      <input v-model="formData.first_name" type="text" name="First Name" placeholder="First Name" :class="{'input-error': error}" @change="error = false">
      <input v-model="formData.last_name" type="text" name="Last Name" placeholder="Last Name" :class="{'input-error': error}" @change="error = false">
      <input v-model="formData.email" type="email" name="Email" placeholder="Email" :class="{'input-error': error}" @change="error = false">
      <input v-model="formData.phone" type="text" name="Phone Number" placeholder="Phone Number" :class="{'input-error': error}" @change="error = false">
      <button type="submit" class="form-btn">Submit</button>
    </form>
</template>

<script>
export default {
    name: 'Form',
    props: ['slogan'],
        data() {
      return {
        formData: {
          business_name: '',
          first_name: '',
          last_name: '',
          email: '',
          phone: '',
        },
        error: false
      }
    },
    methods: {
      
    }
}
</script>

<style>
  form {
    display: flex;
    flex-direction: column;
    align-items: center;
    width: 500px;
    box-shadow: 0 2px 15px 8px rgba(0, 0, 0, 0.164); 
    padding: 20px;
    border-radius: 5px;
    background: var(--white);
  }

  .hidden-input {
    display: none;
  }

  input {
    padding: 10px;
    border: .5px solid #b4b4b4;
    border-radius: 3px;
    margin-bottom: 10px;
    font-size: 1.1rem;
    width: 95%;
  }

  .form-btn {
    padding: 10px;
    background: var(--main);
    color: white;
    font-weight: bold;
    font-size: 1.25rem;
    border: none;
    border-radius: 3px;
    width: 100%;
    cursor: pointer;
  }

  .slogan {
    font-size: 1.5rem;
    font-weight: bold;
    margin-bottom: 10px;
  }

  @media screen and (max-width: 767px) {
    .slogan {
      font-size: 1rem;
    }

    form {
      box-shadow: none;
      border-radius: 0;
    }
  }
</style>
