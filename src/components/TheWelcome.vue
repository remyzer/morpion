<script>
export default  {
  name:'morpion',
  data() {
    return {
      list: ["X", "O", "X", "O", "X", "O", "X", "O", "X"],
      cell1: null,
      cell2: null,
      cell3: null,
      cell4: null,
      cell5: null,
      cell6: null,
      cell7: null,
      cell8: null,
      cell9: null
    }
  },
  methods: {
   play: function(selectedElement){
    if(selectedElement == null){
      return this.list.shift(); 
    }
    else {
      return selectedElement;
    }
   },
   checkIfWinner: function(){
      
   }
  }
}
</script>
<template>
  <div class="grid">
    <div class="row">
      <div class="cell" v-on:click="cell1 = play(cell1), checkIfWinner()"><p>{{cell1}}</p></div>
      <div class="cell" v-on:click="cell2 = play(cell2), checkIfWinner()"><p>{{cell2}}</p></div>
      <div class="cell" v-on:click="cell3 = play(cell3), checkIfWinner()"><p>{{cell3}}</p></div>
    </div>
    <div class="row">
      <div class="cell" v-on:click="cell4 = play(cell4), checkIfWinner()"><p>{{cell4}}</p></div>
      <div class="cell" v-on:click="cell5 = play(cell5), checkIfWinner()"><p>{{cell5}}</p></div>
      <div class="cell" v-on:click="cell6 = play(cell6), checkIfWinner()"><p>{{cell6}}</p></div>
    </div>
    <div class="row">
      <div class="cell" v-on:click="cell7 = play(cell7), checkIfWinner()"><p>{{cell7}}</p></div>
      <div class="cell" v-on:click="cell8 = play(cell8), checkIfWinner()"><p>{{cell8}}</p></div>
      <div class="cell" v-on:click="cell9 = play(cell9), checkIfWinner()"><p>{{cell9}}</p></div>
    </div>
  </div>
</template>
<style>
body {
  background-color: rgb(47, 47, 47);
}
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
  display: table-cell;
  background-color: white;

}
p {
  color: black;
  margin: 50px;
  font-size: 60px ;
  float: start;
}
</style>