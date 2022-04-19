<script setup lang="ts">
import { ref } from 'vue';
import Card from './Card.vue'
import Badge from './Badge.vue'
</script>

<template>
  <Card class="reservation-card">
    <span>Jhon</span>
    <Badge class="vip-badge">
      <span>VIP</span>
    </Badge>
  </Card>
  <Card class="reservation-card">
    <span>aaaaa</span>
    <Badge class="normal-badge">
      <span>NORMAL</span>
    </Badge>
  </Card>
  <Card class="reservation-card">
    <span>ddddd</span>
    <Badge class="vip-badge">
      <span>VIP</span>
    </Badge>
  </Card>
</template>

<style scoped>
.vip-badge {
  background-color: red;
  color: white;
}

.normal-badge {
  background-color: blue;
  color: white;
}

.reservation-card {
  width: 300px;
  height: 80px;
  background-color: antiquewhite;
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin-bottom: 8px;
}
</style>