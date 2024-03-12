
<script setup>
import { ref, watch, computed } from 'vue';
import UnorderedList from '../components/UnorderedList.vue'
import CounterElement from '../components/CounterElement.vue'

const items = ref(['A', 'B', 'C']);

const list = () => {
  items.value.unshift(items.value.pop());
}

const count = ref(5);

const decrementCount = () => {
    count.value--;
}

const textColor = computed(() => count.value >= 0 ? 'green' : 'red');
</script>

<template>
  <main>
    <UnorderedList :items="items">
      <button @click="list">Click me</button>
    </UnorderedList>

    <CounterElement :count="count" @decrement="decrementCount" :textColor="textColor">
      <button @click="decrementCount">Click me</button>
    </CounterElement>
    
  </main>
</template>