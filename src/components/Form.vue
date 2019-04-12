<template>
    <form @submit.prevent="handleSubmit" action="/" name="Free Assessment Form" method="post">
      <span class="slogan">{{ slogan }}</span>
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
        if(this.formData.business_name == '' || this.formData.business_name == null) {
          this.error = true 
          return;
        }
        if(this.formData.first_name == '' || this.formData.first_name == null) {
          this.error = true
          return;
          }
        if(this.formData.last_name == '' || this.formData.last_name == null) {
          this.error = true
          return;
          }
        if(this.formData.email == '' || this.formData.email == null) {
          this.error = true
          return;
          }
        if(this.formData.phone == '' || this.formData.phone == null) {
          this.error = true
          return;
          }
        fetch('/', {
          method: 'POST',
          headers: { 'Content-Type': 'application/x-www-form-urlencoded' },
          body: this.encode({
            'form-name': e.target.getAttribute('name'),
                ...this.formData
          }),
        })
        .then(() => {
          this.formData.business_name = ''
          this.formData.first_name = ''
          this.formData.last_name = ''
          this.formData.email = ''
          this.formData.phone = ''
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
