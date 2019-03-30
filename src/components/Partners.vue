<template>
  <div class="partners">
    <h2 class="partners-header">Partnerships</h2>
    <div class="partners-content">
      <Partner :icon="'dns'" :title="'Partner Title'" />
      <Partner :icon="'dns'" :title="'Partner Title'" />
      <Partner :icon="'dns'" :title="'Partner Title'" />
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
    align-items: center
  }

  .partners-header {
     font-size: 2.0rem;
    margin-top: 0;
    color: var(--main);
  }

  .partners-content {
    background-color: var(--gray);
    width: 100%;
    display: flex;
    justify-content: space-between;
    padding: 50px 0;
  }
</style>
