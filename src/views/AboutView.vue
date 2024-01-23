<script setup>
import { useCounterStore } from '@/stores/counter';

const storeCounter = useCounterStore()
</script>

<template>
<div class="about">
  <h1>About</h1>
  <button 
  @click="storeCounter.increaseCount"
  class="counter-btn">
    {{ storeCounter.count }}
  </button>
</div>
</template>

<style>
.about {
  text-align: center;
}
.counter-btn {
  font-size: 50px;
}
</style>
