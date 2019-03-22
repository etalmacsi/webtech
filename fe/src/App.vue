<template>
  <div id="app">
    <input v-model="message" placeholder="edit me">
    <button @click="onClick(message)">Add</button>
    <div  v-for="(item) in items">
      {{item.message}}
    </div>
  </div>
</template>

<script>
export default {
  name: 'app',
  data(){
    return{
      message: '',
      items:''
    }
  },
  methods: {
    onClick(message){
      this
              .axios
              .post('http://localhost:8082/todo',{message})
              .then( resp => {})
    },
  },
  mounted() {
      let items
      this
              .axios
              .get('http://localhost:8082/todo')
              .then( resp => {
                //console.log(resp.data);
                this.items=resp.data
              });
      console.log("items")
      this.items=items
      console.log(this.items)
  }
}
</script>

<style>

</style>
