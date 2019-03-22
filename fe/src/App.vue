<template>
  <div id="app">
    Cica {{v}}
    <hr>
    <button @click="v++">+</button>
    <button @click="v--">-</button>
  </div>
</template>

<script>
export default {
  name: 'app',
  data: () => ({
    v: 1
  })
}
</script>

<style>
</style>
