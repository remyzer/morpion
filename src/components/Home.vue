<template>
<div>
  <p>Jeu qui se joue à deux joueurs, sur un damier de 3 cases par 3 cases.</p>
  <p>Chaque joueur est représenté par un "symbole"</p>
  <p>Un joueur utilise toujours le même type de "symbole"</p>
  <p>Un premier joueur dessine son symbole sur une case. Puis c'est au tour de l'autre joueur de dessiner son symbole sur une case vide.</p>
  <p>Le but du jeu est de réussir à aligner ses trois symboles (horizontal, vertical ou diagonale), on remporte alors la partie.</p>
  <p>Si la grille est remplie et qu'aucune ligne ne comporte trois symboles identiques, les joueurs finissent par un match nul.</p>
</div>
</template>

<script>
export default {
  name: "Home"
}
</script>