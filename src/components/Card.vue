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
  <div class="cards" ref="cards">
    <div class="card card--back" ref="card-back">
      <div class="card__header card__header--back"></div>
      <div class="card__body card__body--back">
        <div class="card__body--back__panel">{{ card.cvv || '***' }}</div>
        <span class="card__body--back__cvv">CVV</span>
      </div>
    </div>

    <div class="card card--front" ref="card-front">
      <div class="card__header card__header--front">
        <Visa />
        <Signal />
      </div>
      <div class="card__body card__body--front">
        <span>{{ card.number || '**** **** **** ****' }}</span>
      </div>
      <div class="card__footer">
        <span class="opacity-5">{{ card.name || 'Seu nome aqui' }}</span>
        <span class="opacity-5">{{ card.expiration || '**/**' }}</span>
      </div>
    </div>
  </div>
</template>

<style lang="scss" scoped>
.cards {
  position: relative;
  width: 280px;
  transition: 0.3s linear;
}
.card {
  background-image: url('@/assets/images/card-bg.jpg');
  background-size: 110%;
  background-position-x: -10px;
  background-repeat: no-repeat;
  width: 280px;
  height: 170px;
  color: var(--gray-050);
  border: 1px solid var(--gray-700);
  border-radius: 16px;
  margin-top: 16px;

  &--front {
    position: relative;
    padding: 16px 24px 24px 24px;
  }

  &--back {
    position: absolute;
    transform: rotateY(180deg);
  }

  &__header {
    &--front {
      display: flex;
      justify-content: space-between;
      align-items: center;
      margin-bottom: 40px;
    }

    &--back {
      background-color: var(--gray-900);
      height: 32px;
      margin-top: 16px;
    }
  }

  &__body {
    display: flex;

    &--front {
      gap: 18px;
      font-size: 16px;
      line-height: 16px;
      letter-spacing: 4px;
      margin-bottom: 24px;
    }

    &--back {
      font-size: 14px;
      line-height: 16px;
      align-items: center;
      gap: 8px;
      padding: 0 24px;
      margin-top: 48px;

      &__panel {
        background-color: var(--gray-300);
        width: 100%;
        color: var(--gray-900);
        text-align: end;
        border-radius: 4px;
        padding: 9px 12px;
      }
    }
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
