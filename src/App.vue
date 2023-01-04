<template>
  <header id="navBlock">
      <nav>
       <RouterLink to="/"> <button>Home</button></RouterLink>
       <RouterLink to="/game"> <button>Game </button></RouterLink>
      </nav>
  </header>
  <main>
    <RouterView/>
  </main>
</template>



