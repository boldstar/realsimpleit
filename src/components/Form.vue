<template>
    <form action="">
      <span class="slogan">{{ slogan }}</span>
      <input type="text" name="Business Name" placeholder="Business Name">
      <input type="text" name="First Name" placeholder="First Name">
      <input type="text" name="Last Name" placeholder="Last Name">
      <input type="email" name="Email" placeholder="Email">
      <input type="text" name="Phone Number" placeholder="Phone Number">
      <button type="button" class="form-btn">Submit</button>
    </form>
</template>

<script>
export default {
    name: 'Form',
    props: ['slogan']
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
