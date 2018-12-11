<template>
  <header class="home">
    <h1>
      Welkom bij Beau-tique
    </h1>
    <h2>
      Ontdek onze producten en leer meer over ons!
    </h2>
    <div class="foto">
      <img src="@/assets/boutique.jpg" alt="Foto van boutique">
      <router-link class="betreden" to="/producten">Kom binnen</router-link>
    </div>
  </header>
</template>

<script>


export default {


}
</script>

<style scoped>
header h1 {
  font-size: 8rem;
  color: #41B883;
}

header h2 {
  color: black;
  font-size: 3rem;
}

.foto {
  margin-top: 8rem;
  position: relative;
  width: 850px;
}

.foto img {
  width: 100%;
}

.foto .betreden {
  position: absolute;
  bottom: 125px;
  left: 170px;
  width: 150px;
  text-align: center;
  background: #8FD5B5;
  border: 6px solid #41B883;
  padding: 1rem;
  font-size: 2rem;
  color: white;
  text-transform: uppercase;
  transition: color 0.4s;
}

.betreden:hover {
  color: darkslategray;
}


</style>

