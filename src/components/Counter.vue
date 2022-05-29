<template>
  <div>
    <h1>Le compteur a pour valeur : {{counter}}</h1>
    <button @click="counterDecrement">-</button>
    <button @click="counterIncrement">+</button>
  </div>
</template>

<script>
import {ref} from "vue"
export default {
  setup() {
    let counter = ref(0)

    const counterDecrement = () => {
      if(counter.value <= 0) {
        return counter.value
      }
      return counter.value--
    }
    const counterIncrement = () => {
      return counter.value++
    }

    return {
      counter, 
      counterDecrement,
      counterIncrement
    }
  }
}
</script>

<style>

</style>