<script>
import Container from '@/components/Container.vue'
import Forms from '@/components/Forms.vue'
import Submit from '@/components/Submit.vue'

export default {
  name: 'App',
  components: {
    Container,
    Forms,
    Submit
  },
  methods: {
    handleSubmit() {
      // const { number, name, expiration, cvv } = this.$refs.form.$el.elements
    }
  }
}
</script>

<template>
  <Container>
    <div class="panel">
      <div class="panel__row">
        <Forms ref="form" />
      </div>
      <Submit @click="handleSubmit">Adicionar cartão</Submit>
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
  }
}
</style>
