<script lang="ts">
import Visa from '../components/icons/Visa.vue'
import Signal from '../components/icons/Signal.vue'

export default {
  name: 'Card',
  components: {
    Visa,
    Signal
  },
  props: {
    card: { type: Object }
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
      <span>{{ card.number || '**** **** **** ****' }}</span>
    </div>
    <div class="card__footer">
      <span class="opacity-5">{{ card.name || 'Seu nome aqui' }}</span>
      <span class="opacity-5">{{ card.exporation || '**/**' }}</span>
    </div>
  </div>
</template>

<style lang="scss" scoped>
.card {
  background-image: url('@/assets/images/card-bg.png');
  background-size: cover;
  background-repeat: no-repeat;
  width: 280px;
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
    color: var(--gray-050);
    font-size: 14px;
    line-height: 16px;
  }
}
</style>
