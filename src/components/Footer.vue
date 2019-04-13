<template>
    <footer class="footer">
      <div class="footer-content">
        <span>Real.Simple.IT</span>
        <div class="footer-details">
           <span>1510 I45 North, Suite 150 <br>Conroe TX, 77301</span>
          <span>832-879-0478</span>
        </div>
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
    padding: 30px 100px;
    background-color: var(--gray);
    font-size: 1.1rem;
    font-weight: bold;
    color: white;
    position: relative;
  }

  .footer-content {
    display: flex;
    justify-content: space-between;
    width: 100%;
    max-width: 1120px;
    margin: 0 auto;
  }

  .footer-details {
    display: flex;
    flex-direction: column;
  }

  @media screen and (max-width: 767px) {
    footer {
      padding: 30px 50px;
      font-size: .8rem;
    }
  }
</style>
