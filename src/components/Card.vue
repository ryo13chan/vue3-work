<script setup lang="ts">

</script>

<template>
  <div class="card">
    <slot></slot>
  </div>
</template>

<style scoped>
.container {
  display: flex;
  flex-direction: column;
  align-items: center;
}

.card {
  box-shadow: 4px 4px 4px gray;
  border-radius: 8px;
  padding: 20px;
}
</style>