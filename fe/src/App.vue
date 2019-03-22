<template>
  <div id="app">
    <table>
      <tr :key="i" v-for="(row,i) in t">
        <td :key="j" v-for="(cell,j) in row">
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
      t: Array(20)
        .fill(0)
        .map( () => 
          Array(20)
            .fill(0)
            .map( () => "" )
        )
    }
  }
}
</script>

<style>
 td {
   width:15px;
   height:15px;
   border-radius: 3px;
   background-color: aqua ;
   box-shadow: 1px 1px 4px black;
   cursor:pointer;
 }
</style>
