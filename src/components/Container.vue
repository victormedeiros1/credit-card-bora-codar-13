<script lang="ts">
export default {
  name: 'Container'
}
</script>

<template>
  <div class="container"><slot /></div>
</template>

<style lang="scss" scoped>
.container {
  width: 100%;
  min-height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  padding: 0 20px;
}
</style>
