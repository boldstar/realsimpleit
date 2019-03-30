<template>
    <footer class="footer">
      <span>Real Simple IT</span>
      <div class="footer-details">
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
    padding: 30px 100px;
    background-color: var(--gray);
    font-size: 1.1rem;
    font-weight: bold;
    color: white;
    position: relative;
  }

  .footer-details {
    display: flex;
    flex-direction: column;
  }
</style>
