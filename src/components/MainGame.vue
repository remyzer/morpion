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
    /**
     * Return the values of the first element in the list if the selected element is null.
     * Else return the selected element to prevent clicking on the same cell.
     * @param {string} selectedElement 
     */
   play: function(selectedElement){
      if(selectedElement == null){
        return this.list.shift();
      }
      else {
        return selectedElement;
      }
   },
   /**
    * Checks every winning condition and call the method endGame or set the property isDraw if the game is a draw.
    */
   checkIfWinner: function(){
      if(this.cell1 === this.cell2 && this.cell2 === this.cell3 && this.cell1 != null){

        this.endGame(this.cell1);
      } else if(this.cell4 === this.cell5 && this.cell5 === this.cell6 && this.cell4 != null){

        this.endGame(this.cell4);
      } else if(this.cell7 === this.cell8 && this.cell8 === this.cell9 && this.cell7 != null){

        this.endGame(this.cell7);
      }else if(this.cell1 === this.cell4 && this.cell4 === this.cell7 && this.cell1 != null){

        this.endGame(this.cell1);
      }else if(this.cell2 === this.cell5 && this.cell5 === this.cell8 && this.cell2 != null){

        this.endGame(this.cell2);
      }else if(this.cell3 === this.cell6 && this.cell6 === this.cell9 && this.cell3 != null){

        this.endGame(this.cell3);
      } else  if(this.cell1 === this.cell5 && this.cell5 === this.cell9 && this.cell1 != null){

        this.endGame(this.cell1);
      }else  if(this.cell3 === this.cell5 && this.cell5 === this.cell7 && this.cell3 != null){

        this.endGame(this.cell3);
      }else if(this.list.length === 0){
        this.isDraw = true;
      }
   },
   /**
    * This function is called when a winning condition has been triggered.
    * The parameter is the value of one cell, it's used to define the winningSymbol.
    * This function set the list to an empty list so it's not possible to put symbols in the cells
    * @param {string} winningSymbol 
    */
   endGame: function(winningSymbol){
      this.list = [];
      this.isFinished = true;
      this.winningSymbol = winningSymbol;
   },
   /**
    * This function is called when the user click on the reset button.
    */
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
  <div class="content">
    <div class="grid">
      <div class="row">
        <div class="cell" v-on:click="cell1 = play(cell1), checkIfWinner()"><p class="cellText">{{cell1}}</p></div>
        <div class="cell" v-on:click="cell2 = play(cell2), checkIfWinner()"><p class="cellText">{{cell2}}</p></div>
        <div class="cell" v-on:click="cell3 = play(cell3), checkIfWinner()"><p class="cellText">{{cell3}}</p></div>
      </div>
      <div class="row">
        <div class="cell" v-on:click="cell4 = play(cell4), checkIfWinner()"><p class="cellText">{{cell4}}</p></div>
        <div class="cell" v-on:click="cell5 = play(cell5), checkIfWinner()"><p class="cellText">{{cell5}}</p></div>
        <div class="cell" v-on:click="cell6 = play(cell6), checkIfWinner()"><p class="cellText">{{cell6}}</p></div>
      </div>
      <div class="row">
        <div class="cell" v-on:click="cell7 = play(cell7), checkIfWinner()"><p class="cellText">{{cell7}}</p></div>
        <div class="cell" v-on:click="cell8 = play(cell8), checkIfWinner()"><p class="cellText">{{cell8}}</p></div>
        <div class="cell" v-on:click="cell9 = play(cell9), checkIfWinner()"><p class="cellText">{{cell9}}</p></div>
      </div>
    </div>
    <button v-on:click="resetGame()" >Reset</button>
    <div v-if="isDraw">
      <p class="endText">Egalité !</p>
    </div>
    <div v-if="isFinished">
      <p class="endText">Le joueur "{{ winningSymbol }}" a gagné !</p>
    </div>
  </div>
</template>