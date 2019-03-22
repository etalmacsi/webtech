<template>
  <div id="app">
    <table>
      <tr :key="i" v-for="(row,i) in t">
        <td :key="j" 
            v-for="(cell,j) in row"
            @click="f(i,j)">
          {{cell}}
        </td>
      </tr>
    </table>
  </div>
</template>

<script>
export default {
  name: 'app',
  data() {
    return {
      next: "X",
      t: Array(14)
        .fill(0)
        .map( () => 
          Array(14)
            .fill(0)
            .map( () => "" )
        )
    }
  },
  methods: {
    f(i,j) {
      this.$set(
        this.t[i],
        j,
        this.next==='X'?this.next='O':this.next='X')
    }
  }
}
</script>

<style>
 td {
   text-align: center;
   width:20px;
   height:20px;
   border-radius: 3px;
   background-color: aqua ;
   box-shadow: 1px 1px 4px black;
   cursor:pointer;
 }
</style>
