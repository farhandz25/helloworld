<script setup>
  import { ref } from 'vue'
  const message = ref('world')

  const greeting = ref('nama saya')
  const name = ref('Farhan Dzaky Aqila') 

  const inputvalue = ref('')

  const count = ref (0)

  function increment() {
    count.value++
  }
    const buttonclass = ref('normal-btn')
    const toggleButtonClass = () => {
      buttonclass.value = buttonclass.value === 'normal-btn' ? 'active-btn' : 'normal-btn'
    }

    const isVisible = ref(true)
</script>

<template>
  <h1>{{ message }}</h1>

  <h1>{{ greeting }} {{ name }}</h1>

  <input v-model="inputvalue" placeholder="hasil" />
  <p>hasil: {{ inputvalue }}</p>

  <button v-on:click="increment">click</button>
  <p>counter: {{ count }}</p>

  <button v-bind:class="buttonclass" @click="toggleButtonClass">klik</button>

  <button @click="isVisible = !isVisible">klik</button>
  <p v-if="isVisible">nama saya farhan</p>
  <p v-else>20</p>
</template>

<style scoped>
.normal-btn {
  background-color: red;
  color: black;
}
.active-btn {
  background-color: blue;
  color: black;
}
</style>