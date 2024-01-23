<script setup>
import { ref, computed } from 'vue';
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
    {{ count }}
  </div>
  <div class="buttons">
    <button @click="decreamentCount">-</button>
    <button @click="increaseCount">+</button>
  </div>
  <hr>
  <div>
    This Counter is: {{ oddOrEven }}
  </div>
</div>
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
