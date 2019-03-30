<template>
    <footer class="footer">
      <span>Real Simple IT</span>
      <div class="details">
        <span>Address</span>
        <span>Phone Number</span>
        <span>Social Media</span>
      </div>
    </footer>
</template>

<script>
export default {
    name: 'Footer'
}
</script>

<style>
  footer {
    display: flex;
    justify-content: space-between;
    padding: 30px 50px;
    background-color: gray;
  }

  .details {
    display: flex;
    flex-direction: column;
  }
</style>
