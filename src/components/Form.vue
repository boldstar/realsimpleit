<template>
  <form 
    name="free_network_assessment"
    method="post"
    v-on:submit.prevent="handleSubmit"
    action="/success/"
    data-netlify="true"
    data-netlify-honeypot="bot-field"
  >
  <p class="slogan">{{slogan}}</p>
  <input type="hidden" name="form-name" value="contact" />
  <p hidden>
    <label>
      Don’t fill this out: <input name="bot-field" />
    </label>
  </p>
    <div class="input-group">
      <label for="business_name" class="label" >Business Name</label>
      <input type="text" name="business_name" v-model="formData.business_name" :class="{'input-error': error}" @change="error = false"/>
    </div>
    <div class="input-group">
      <label for="first_name" class="label" >First Name</label>
      <input type="text" name="first_name" v-model="formData.first_name" :class="{'input-error': error}" @change="error = false"/>
    </div>
    <div class="input-group">
      <label for="last_name" class="label" >Last Name</label>
      <input type="text" name="last_name" v-model="formData.last_name" :class="{'input-error': error}" @change="error = false"/>
    </div>
    <div class="input-group">
      <label for="email">Email</label>
      <input type="email" name="email" v-model="formData.email" :class="{'input-error': error}" @change="error = false"/>
    </div>
    <div class="input-group">
      <label for="phone">Phone Number</label>
      <input type="text" name="phone" v-model="formData.phone" :class="{'input-error': error}" @change="error = false"/>
    </div>
  <button type="submit" class="form-btn">Submit</button>

  <Modal class="success-modal" v-if="success" @close-modal="removeModal"/>
</form>
</template>

<script>
import Modal from '@/components/Modal.vue'
export default {
  name: 'Form',
  props: ['slogan'],
  components: {
    Modal
  },
  data() {
    return {
      formData: {},
      success: false,
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
        ...this.formData,
      }),
    })
    .then(() => {
      this.formData = ""
      this.$router.push('/')
      this.success = true
    })
    .catch(error => alert(error))
  },
  removeModal() {
    this.success = false
  }
}
}
</script>

<style>
  .success-modal {
    position: absolute;
    top:0;
    left: 0;
  }

  form {
    display: flex;
    flex-direction: column;
    align-items: center;
    width: 500px;
    box-shadow: 0 2px 15px 8px rgba(0, 0, 0, 0.164); 
    padding: 15px;
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
    margin-top: 0;
  }

  .input-error {
    border: 1px solid red;
  }

  .input-group {
    width: 100%;
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
