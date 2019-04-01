<template>
  <div class="partners">
    <h2 class="partners-header">Partnerships</h2>
    <div class="partners-background">
      <div class="partners-content">
        <Partner :icon="'dns'" :title="'Partner Title'" />
        <Partner :icon="'dns'" :title="'Partner Title'" />
        <Partner :icon="'dns'" :title="'Partner Title'" />
      </div>
    </div>
  </div>
</template>

<script>
import Partner from '@/components/Partner.vue'
export default {
    name: 'Partners',
    components: {
      Partner
    }
}
</script>

<style>
  .partners {
    display: flex;
    flex-direction: column;
    align-items: center;
  }

  .partners-header {
    font-size: 2.0rem;
    margin-top: 0;
    color: var(--main);
  }

  .partners-background {
    background-color: var(--gray);
    width: 100%;
  }

  .partners-content {
    width: 100%;
    max-width: 1120px;
    display: flex;
    justify-content: space-between;
    padding: 50px 0;
    margin: 0 auto;
  }
</style>
