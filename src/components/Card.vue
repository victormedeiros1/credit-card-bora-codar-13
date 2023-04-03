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
  },
  watch: {
    'card.cvv'() {
      const cards = this.$refs.cards
      const cardBack = this.$refs['card-back']

      if (cards.classList.value.includes('rotate') && this.card.cvv.length === 0) {
        cards.classList.remove('rotate')
        setTimeout(() => cardBack.classList.remove('z-index-1'), 150)
      } else {
        cards.classList.add('rotate')
        setTimeout(() => cardBack.classList.add('z-index-1'), 150)
      }
    }
  }
}
</script>

<template>
  <div class="cards" ref="cards">
    <div class="card card--back" ref="card-back">
      <div class="card__header">
        <Visa />
        <Signal />
      </div>
      <div class="card__body">
        <span>BACK</span>
      </div>
      <div class="card__footer">
        <span class="opacity-5">{{ card.name || 'Seu nome aqui' }}</span>
        <span class="opacity-5">{{ card.exporation || '**/**' }}</span>
      </div>
    </div>

    <div class="card card--front">
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
  </div>
</template>

<style lang="scss" scoped>
.cards {
  position: relative;
  width: 280px;
  height: 170px;
  transition: 0.3s linear;
}
.card {
  position: absolute;
  background-image: url('@/assets/images/card-bg.jpg');
  background-size: 110%;
  background-position-x: -10px;
  background-repeat: no-repeat;
  width: 280px;
  height: fit-content;
  color: var(--gray-050);
  border: 1px solid var(--gray-700);
  border-radius: 16px;
  padding: 16px 24px 24px 24px;
  margin-top: 16px;

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

  &--back {
    transform: rotateY(180deg);
  }
}

.rotate {
  transform: rotateY(180deg);
}
</style>
