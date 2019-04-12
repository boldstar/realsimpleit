<template>
    <form 
  name="contact"
  method="post"
  v-on:submit.prevent="handleSubmit"
  action="/success/"
  data-netlify="true"
  data-netlify-honeypot="bot-field"
>
  <input type="hidden" name="form-name" value="contact" />
  <p hidden>
    <label>
      Don’t fill this out: <input name="bot-field" />
    </label>
  </p>
  <div class="sender-info">
    <div>
      <label for="name" class="label" >Your name</label>
      <input type="text" name="name" v-model="formData.name" />
    </div>
    <div>
      <label for="first_name" class="label" >Your name</label>
      <input type="text" name="first_name" v-model="formData.name" />
    </div>
    <div>
      <label for="last_name" class="label" >Your name</label>
      <input type="text" name="last_name" v-model="formData.name" />
    </div>
    <div>
      <label for="email">Your email</label>
      <input type="email" name="email" v-model="formData.email" />
    </div>
    <div>
      <label for="phone">Your email</label>
      <input type="text" name="phone" v-model="formData.phone" />
    </div>
  </div>

  <div class="message-wrapper">
    <label for="message">Message</label>
    <textarea name="message" v-model="formData.message"></textarea>
  </div>

  <button type="submit">Submit form</button>
</form>
</template>

<script>
export default {
  name: 'Form',
  props: ['slogan'],
    data() {
  return {
    formData: {},
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
        'form-name': e.target.getAttribute('name'),
        ...this.formData,
      }),
    })
    .then(() => this.$router.push('/success'))
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
