<script>
export default  {
  name:'morpion',
  data() {
    return {
      list: ["X", "O", "X", "O", "X", "O", "X", "O", "X"],
      cell1: "",
      cell2: "",
      cell3: "",
      cell4: "",
      cell5: "",
      cell6: "",
      cell7: "",
      cell8: "",
      cell9: ""
    }
  },
  methods: {

  }
}
</script>

<template>
  <div class="grid">
    <div class="row">
      <div class="cell" v-on:click="cell1 = this.list.shift();"><p>{{cell1}}</p></div>
      <div class="cell" v-on:click="cell2 = this.list.shift();"><p>{{cell2}}</p></div>
      <div class="cell" v-on:click="cell3 = this.list.shift();"><p>{{cell3}}</p></div>
    </div>
    <div class="row">
      <div class="cell" v-on:click="cell4 = this.list.shift();"><p>{{cell4}}</p></div>
      <div class="cell" v-on:click="cell5 = this.list.shift();"><p>{{cell5}}</p></div>
      <div class="cell" v-on:click="cell6 = this.list.shift();"><p>{{cell6}}</p></div>
    </div>
    <div class="row">
      <div class="cell" v-on:click="cell7 = this.list.shift();"><p>{{cell7}}</p></div>
      <div class="cell" v-on:click="cell8 = this.list.shift();"><p>{{cell8}}</p></div>
      <div class="cell" v-on:click="cell9 = this.list.shift();"><p>{{cell9}}</p></div>
    </div>
  </div>
</template>

<style>
.grid {
  display: table;
  border-spacing: 5px
}
.row {
  display: table-row
}
.cell {
  width: 150px;
  height: 150px;
  background: white;
  display: table-cell;
}
p {
  color: black;
  margin: 50px;
  font-size: 60px ;
  float: start;
}
</style>