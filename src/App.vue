<script>
import Container from '@/components/Container.vue'
import Submit from '@/components/Submit.vue'
import Security from '@/components/Security.vue'
import Card from '@/components/Card.vue'
import { mask } from 'vue-the-mask'

export default {
  name: 'App',
  components: {
    Container,
    Submit,
    Card,
    Security
  },
  data() {
    return {
      card: {
        number: '',
        name: '',
        expiration: '',
        cvv: ''
      }
    }
  },
  directives: {
    mask
  },
  methods: {
    rotateCard() {
      const cards = document.querySelector('.cards')
      const cardBack = document.querySelector('.card--back')

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
  <Container>
    <div class="panel">
      <div class="panel__row">
        <form class="form">
          <div class="form__group">
            <label for="number" class="form__label">Número do cartão</label>
            <input
              id="number"
              class="form__field"
              name="number"
              placeholder="**** **** **** ****"
              v-model="card.number"
              v-mask="'#### #### #### ####'"
            />
          </div>

          <div class="form__group">
            <label id="name" class="form__label">Nome do titular</label>
            <input
              for="name"
              class="form__field"
              type="text"
              name="name"
              placeholder="Nome como está no cartão"
              v-model="card.name"
              maxLength="26"
            />
          </div>

          <div class="form__footer">
            <div class="form__group">
              <label for="expiration" class="form__label">Validade</label>
              <input
                id="expiration"
                class="form__field"
                type="text"
                name="expiration"
                placeholder="mm/aa"
                v-model="card.expiration"
                v-mask="'##!/##'"
              />
            </div>
            <div class="form__group max-w-130">
              <label for="cvv" class="form__label">CVV</label>
              <input
                id="cvv"
                class="form__field"
                type="text"
                name="cvv"
                placeholder="***"
                v-model="card.cvv"
                v-mask="'###'"
                @focusin="rotateCard"
                @focusout="rotateCard"
              />
            </div>
          </div>
          <div class="d-mobile">
            <Security />
          </div>
        </form>
        <div class="panel__card-wrapper">
          <Card :card="card" />
          <div class="d-desktop">
            <Security />
          </div>
        </div>
      </div>
      <Submit>Adicionar cartão</Submit>
    </div>
  </Container>
</template>

<style lang="scss" scoped>
.panel {
  background-color: var(--gray-800);
  width: 100%;
  max-width: 736px;
  border: 1px solid var(--gray-700);
  border-radius: 8px;
  padding: 32px;

  &__row {
    display: flex;
    gap: 64px;

    @media (max-width: 576px) {
      flex-direction: column-reverse;
      gap: 48px;
    }
  }

  &__card-wrapper {
    display: flex;
    flex-direction: column;
    align-items: center;
  }
}
.form {
  display: flex;
  flex-direction: column;
  gap: 24px;

  &__group {
    display: flex;
    flex-direction: column;
  }
  &__label {
    color: var(--gray-200);
    font-size: 14px;
    line-height: 16px;
    margin-bottom: 4px;
  }
  &__field {
    width: 100%;
    background-color: var(--gray-900);
    color: var(--gray-100);
    font-size: 16px;
    line-height: 24px;
    border-radius: 4px;
    border: 1px solid var(--gray-700);
    padding: 12px;
  }
  &__footer {
    display: flex;
    gap: 24px;
  }
}
</style>
