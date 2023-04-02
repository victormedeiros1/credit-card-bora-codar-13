<script lang="ts">
import Visa from '../components/icons/Visa.vue'
import Signal from '../components/icons/Signal.vue'

export default {
  name: 'Card',
  components: {
    Visa,
    Signal
  }
}
</script>

<template>
  <div class="card">
    <div class="card__header">
      <Visa />
      <Signal />
    </div>
    <div class="card__body">
      <span class="card__number">4716</span>
      <span class="card__number">8039</span>
      <span class="card__number">02**</span>
      <span class="card__number">****</span>
    </div>
    <div class="card__footer">
      <span>Seu nome aqui</span>
      <span>**/**</span>
    </div>
  </div>
</template>

<style lang="scss" scoped>
.card {
  background-image: url('@/assets/images/card-bg.png');
  background-size: cover;
  background-repeat: no-repeat;
  width: 100%;
  max-width: 280px;
  height: fit-content;
  color: var(--gray-050);
  border: 1px solid var(--gray-700);

  border-radius: 16px;
  padding: 16px 24px 24px 24px;
  margin: 16px 0 32px 0;

  &__header {
    display: flex;
    justify-content: space-between;
    align-items: center;
    margin-bottom: 40px;
  }

  &__body {
    display: flex;
    gap: 18px;
    font-size: 16px;
    line-height: 16px;
    letter-spacing: 4px;
    margin-bottom: 24px;
  }

  &__footer {
    display: flex;
    justify-content: space-between;
    font-size: 14px;
    line-height: 16px;
  }
}
</style>
