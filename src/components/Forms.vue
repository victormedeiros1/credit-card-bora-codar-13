<script lang="ts">
export default {
  name: 'Forms'
}
</script>

<template>
  <form class="form">
    <div class="form__group">
      <label for="number" class="form__label">Número do cartão</label>
      <input id="number" class="form__field" name="number" placeholder="**** **** **** ****" />
    </div>

    <div class="form__group">
      <label id="name" class="form__label">Nome do titular</label>
      <input for="name" class="form__field" name="name" placeholder="Nome como está no cartão" />
    </div>

    <div class="form__footer">
      <div class="form__group">
        <label for="expiration" class="form__label">Validade</label>
        <input id="expiration" class="form__field" name="expiration" placeholder="mm/aa" />
      </div>
      <div class="form__group max-w-130">
        <label for="cvv" class="form__label">CVV</label>
        <input id="cvv" class="form__field" name="cvv" placeholder="***" />
      </div>
    </div>
  </form>
</template>

<style lang="scss" scoped>
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
