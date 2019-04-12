<template>
    <form name="Free Assessment Form" method="post" data-netlify-honeypot="bot-field">
      <span class="slogan">{{ slogan }}</span>
      <input type="hidden" name="form-name" value="contact"  class="hidden"/>
      <input @input="ev => formData.business_name = ev.target.value" type="text" name="Business Name" placeholder="Business Name" :class="{'input-error': error}" @change="error = false">
      <input @input="ev => formData.first_name = ev.target.value" type="text" name="First Name" placeholder="First Name" :class="{'input-error': error}" @change="error = false">
      <input @input="ev => formData.last_name = ev.target.value" type="text" name="Last Name" placeholder="Last Name" :class="{'input-error': error}" @change="error = false">
      <input @input="ev => formData.email = ev.target.value" type="email" name="Email" placeholder="Email" :class="{'input-error': error}" @change="error = false">
      <input @input="ev => formData.phone = ev.target.value" type="text" name="Phone Number" placeholder="Phone Number" :class="{'input-error': error}" @change="error = false">
      <button type="button" class="form-btn" @click="handleSubmit">Submit</button>
    </form>
</template>

<script>
export default {
  name: 'Form',
  props: ['slogan'],
    data() {
    return {
      formData: {},
      error: false
    }
  },
  methods: {
    encode(data) {
    return Object.keys(data)
      .map(key => encodeURIComponent(key) + '=' + encodeURIComponent(data[key]))
      .join('&')
    },
    handleSubmit(e) {
      fetch('/', {
        method: 'POST',
        headers: { 'Content-Type': 'application/x-www-form-urlencoded' },
        body: this.encode({
          'form-name': "Free Assessment Form",
              ...this.formData
        }),
      })
      .then(() => {
        this.formData = ""
        this.$router.push('/')
        alert('Form Submitted!')
      })
      .catch(error => alert(error))
    }
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

  .hidden {
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

  .input-error {
    border: 1px solid red;
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
