<script setup>

import axios from 'axios';

const typeColors = {
  normal: '#A8A77A',
  fire: '#EE8130',
  water: '#6390F0',
  electric: '#F7D02C',
  grass: '#7AC74C',
  ice: '#96D9D6',
  fighting: '#C22E28',
  poison: '#A33EA1',
  ground: '#E2BF65',
  flying: '#A98FF3',
  psychic: '#F95587',
  bug: '#A6B91A',
  rock: '#B6A136',
  ghost: '#735797',
  dragon: '#6F35FC',
  dark: '#705746',
  steel: '#B7B7CE',
  fairy: '#D685AD',
};

window.addEventListener("DOMContentLoaded", function () {

  const pokemonList = this.document.getElementById("pokemonList");

  axios
    .get("https://pokeapi.co/api/v2/pokemon?limit=100&offset=0")
    .then(response => {

      let pokemons = response.data.results;

      pokemons.forEach(pokemon => {
        axios
          .get(pokemon.url)
          .then(pokemonInfo => {
            const content = `<div class="pokemonCard rounded p-2" style="background: linear-gradient(var(--whitePrimary), var(--whiteSecondary)); width: 48%; height: 70%">
          <div class="d-flex align-items-center justify-content-between">
            <h2 class="m-0 h6">${pokemonInfo.data.name.toUpperCase()}</h2>
            <p class="m-0 fs-6">#${pokemonInfo.data.order}</p>
          </div>

          <div class="d-flex align-items-center justify-content-around gap-3">
            <img class="col-3"
              src="${pokemonInfo.data.sprites.other.dream_world.front_default}"
              alt="${pokemonInfo.data.name}" />
            <ul class="list-group text-center">
              ${pokemonInfo.data.types.map(pokemonType => `<li class="list-group-item py-0 px-1" style="background-color:${typeColors[pokemonType.type.name]}">${pokemonType.type.name}</li>`
            ).join("")}
            </ul>
          </div>
        </div>`;
            console.log(pokemonInfo);
            pokemonList.innerHTML += content;

          })

      });
    })

})


</script>

<template>
  <main class="d-flex justify-content-around">
    <div id="pokemonPreview" class="col-4 rounded p-3">
      <div class="d-flex align-items-center justify-content-between">
        <h2 class="m-0">Bulbasaur</h2>
        <p class="m-0 fs-4">#1</p>
      </div>

      <div class="d-flex align-items-center justify-content-between">
        <img class="col-5"
          src="https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/other/official-artwork/1.png"
          alt="Bulbasaur" />

        <ul class="list-unstyled">
          <ul class="list-group list-group-horizontal">
            <li class="list-group-item py-0 px-1 bg-success">GRASS</li>
            <li class="list-group-item py-0 px-1 bg-danger">POISON</li>
          </ul>
          <li>Special attack:</li>
          <li>Special defense:</li>
        </ul>
      </div>

      <ul class="list-unstyled d-flex justify-content-between flex-wrap m-0">
        <li>HP: 45</li>
        <li>Atk: 49</li>
        <li>Def: 49</li>
        <li>Speed: 45</li>
      </ul>

    </div>

    <div class="col-6">
      <input type="text" id="inputPokemon" class="col-12 rounded"
        placeholder="Insira o nome do pokémon para pesquisar. Ex: Pikachu">
      <div id="pokemonList" class="d-flex justify-content-between flex-wrap mt-1 gap-2">
      </div>
    </div>

  </main>
</template>

<style scoped>
main {
  color: var(--darkBluePrimary);
  height: 50vh;
}

#pokemonList {
  height: 85%;

  overflow: auto;
}

#pokemonPreview,
#pokemonList>div {
  background: linear-gradient(var(--whitePrimary), var(--whiteSecondary));
}

.font-small {
  font-size: 60%;
}
</style>
