<script setup>
import { ref, computed } from 'vue';

import { useCounterStore } from '../stores/counter';

import Counter from '@/components/Counter.vue';

const storeCounter = useCounterStore();
  const count = ref(0);

  const increaseCount = () => {
    count.value++;
  }

  const decreamentCount = () => {
    count.value--;
  }

  const oddOrEven = computed(() => {
    if(count.value % 2 === 0) {
      return 'Even'
    }
    else {
      return 'Odd'
    }
  })

</script>

<template>
<div class="home">
  <div class="count">
    {{ storeCounter.count }}
  </div>
  <div class="buttons">
    <button @click="storeCounter.decreaseCount">-</button>
    <button @click="storeCounter.increaseCount">+</button>
  </div>
  <hr>
  <div>
    This Counter is: {{ storeCounter.oddOrEven }}
  </div>
  <hr>
  <div>
    <h3>Edit Counter: </h3>
    <input 
    v-model="storeCounter.count"
    type="number">
  </div>
</div>

<Counter></Counter>
</template>

<style scoped>
.count {
  font-size: 60px;
  text-align: center;
}

.buttons {
  text-align: center;
}
.buttons button {
  font-size: 40px;
  margin: 10px;
  cursor: pointer;
}
</style>
