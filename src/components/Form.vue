<template>
    <form @submit.prevent="validateSubmit" name="Free Assessment Form" data-netlify="true" netlify-honeypot="bot-field">
      <span class="slogan">{{ slogan }}</span>
      <p class="hidden">
        <label>Don’t fill this out if you're human: <input name="bot-field" /></label>
      </p>
      <input @input="ev => business_name = ev.target.value" type="text" name="Business Name" placeholder="Business Name" :class="{'input-error': error}" @change="error = false">
      <input @input="ev => first_name = ev.target.value" type="text" name="First Name" placeholder="First Name" :class="{'input-error': error}" @change="error = false">
      <input @input="ev => last_name = ev.target.value" type="text" name="Last Name" placeholder="Last Name" :class="{'input-error': error}" @change="error = false">
      <input @input="ev => phone = ev.target.value" type="email" name="Email" placeholder="Email" :class="{'input-error': error}" @change="error = false">
      <input @input="ev => email = ev.target.value" type="text" name="Phone Number" placeholder="Phone Number" :class="{'input-error': error}" @change="error = false">
      <button type="submit" class="form-btn">Submit</button>
    </form>
</template>

<script>
export default {
    name: 'Form',
    props: ['slogan'],
    data() {
      return {
        business_name: '',
        first_name: '',
        last_name: '',
        email: '',
        phone: '',
        error: false
      }
    },
    methods: {
      validateSubmit() {
        if(this.business_name == '' || this.business_name == null) {
          this.error = true 
          return;
        }
        if(this.first_name == '' || this.first_name == null) {
          this.error = true
          return;
          }
        if(this.last_name == '' || this.last_name == null) {
          this.error = true
          return;
          }
        if(this.email == '' || this.email == null) {
          this.error = true
          return;
          }
        if(this.phone == '' || this.phone == null) {
          this.error = true
          return;
          }
      }
    }
}
</script>

<style>
  .hidden {
    display: none;
  }

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

  input {
    padding: 10px;
    border: .5px solid #b4b4b4;
    border-radius: 3px;
    margin-bottom: 10px;
    font-size: 1.1rem;
    width: 95%;
  }

  .input-error {
    border: 1px solid red;
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
