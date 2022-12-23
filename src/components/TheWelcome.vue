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
      cell9: null,
      isFinished: false,
      isDraw: false,
      winningSymbol: null
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
      if(this.cell1 == this.cell2 && this.cell2 == this.cell3 && this.cell1 != null){
        
        this.endGame(this.cell1);
        console.log("win !");
      } else if(this.cell4 == this.cell5 && this.cell5 == this.cell6 && this.cell4 != null){
        
        this.endGame(this.cell4);
        console.log("win !");
      } else if(this.cell7 == this.cell8 && this.cell8 == this.cell9 && this.cell7 != null){

        this.endGame(this.cell7);
        console.log("win !");
      }else if(this.cell1 == this.cell4 && this.cell4 == this.cell7 && this.cell1 != null){

        this.endGame(this.cell1);
        console.log("win !");
      }else if(this.cell2 == this.cell5 && this.cell5 == this.cell8 && this.cell2 != null){

        this.endGame(this.cell2);
        console.log("win !");
      }else if(this.cell3 == this.cell6 && this.cell6 == this.cell9 && this.cell3 != null){

        this.endGame(this.cell3);
        console.log("win !");
      } else  if(this.cell1 == this.cell5 && this.cell5 == this.cell9 && this.cell1 != null){

        this.endGame(this.cell1);
        console.log("win !");
      }else  if(this.cell3 == this.cell5 && this.cell5 == this.cell7 && this.cell3 != null){

        this.endGame(this.cell3);
        console.log("win !");
      }else if(this.list.length == 0){
        this.isDraw = true;
      }
   },
   endGame: function(winningSymbol){
      this.list = [];
      this.isFinished = true;
      this.winningSymbol = winningSymbol;
   },
   resetGame: function(){
      this.list = ["X", "O", "X", "O", "X", "O", "X", "O", "X"];
      this.winningSymbol = null;
      this.isFinished = false;
      this.isDraw = false;
      this.cell1 = null;
      this.cell2 = null;
      this.cell3 = null;
      this.cell4 = null;
      this.cell5 = null;
      this.cell6 = null;
      this.cell7 = null;
      this.cell8 = null;
      this.cell9 = null;
   }
  }
}
</script>
<template>
  <div>
    <div v-if="isDraw">
      <p class="endText">Egalité !</p>
    </div>
    <div v-if="isFinished">
      <p class="endText">Le joueur "<span id="winningSymbol">{{ winningSymbol }}</span>" à gagné !</p>
    </div>
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
    <div>
      <button v-on:click="resetGame()" >Reset</button>
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
.endText{
  color: white;
}

#winningSymbol {
  color: salmon;
}
</style>