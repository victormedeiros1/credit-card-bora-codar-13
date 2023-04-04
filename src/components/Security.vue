<script>
import Shield from '@/components/icons/Shield.vue'

export default {
  name: 'Security',
  components: { Shield }
}
</script>

<template>
  <div class="security">
    <Shield />
    <span>Seus dados estão seguros</span>
  </div>
</template>

<style lang="scss" scoped>
.security {
  display: flex;
  justify-content: center;
  color: var(--gray-200);
  gap: 8px;
  margin-top: 32px;
}
</style>
