<script lang="ts">
export default {
  name: 'Submit'
}
</script>

<template>
  <button class="submit"><slot /></button>
</template>

<style lang="scss" scoped>
.submit {
  width: 100%;
  background-color: var(--primary-main);
  color: var(--gray-050);
  font-size: 18px;
  line-height: 24px;
  text-align: center;
  border: none;
  border-radius: 4px;
  margin-top: 48px;
  padding: 16px;
}
</style>
