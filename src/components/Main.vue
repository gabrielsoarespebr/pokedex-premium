<script setup>

import axios from 'axios';

// POKEMON TYPE COLOR GUIDE
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

// POKEMON CLASS TO UPDATE PREVIEW ACCORDING ORDER NUMBER
class Pokemon {
  constructor(name, order, imgUrl, type, spcAtk, spcDef, hp, atk, def, speed) {
    this.name = name;
    this.order = order;
    this.imgUrl = imgUrl;
    this.type = type;
    this.spcAtk = spcAtk;
    this.spcDef = spcDef;
    this.hp = hp;
    this.atk = atk;
    this.def = def;
    this.speed = speed;
  }
};

const pokemonArray = [];

window.addEventListener("DOMContentLoaded", function () {

  const pokemonList = this.document.getElementById("pokemonList");

  // ACCESSING POKE API THROUGH AXIOS
  axios
    .get("https://pokeapi.co/api/v2/pokemon?limit=100&offset=0")
    .then(response => {

      let pokemons = response.data.results;

      pokemons.forEach(pokemon => {
        axios
          .get(pokemon.url)
          .then(pokemonInfo => {
            let pokemonTemp = new Pokemon(
              pokemonInfo.data.name,
              pokemonInfo.data.order,
              pokemonInfo.data.sprites.other.dream_world.front_default,
              pokemonInfo.data.types,
              pokemonInfo.data.stats[3].base_stat,
              pokemonInfo.data.stats[4].base_stat,
              pokemonInfo.data.stats[0].base_stat,
              pokemonInfo.data.stats[1].base_stat,
              pokemonInfo.data.stats[2].base_stat,
              pokemonInfo.data.stats[2].base_stat
            );

            pokemonArray.push(pokemonTemp);
            // CREATING CARD ACCORDING SEARCHBAR INPUT - Default value is a empty string and returns all pokemons
            function updatePreview() {
              console.log("ola");


            }

            if (pokemonInfo.data.name.includes(pokemonInput.value.toLowerCase())) {
              const content = `<div class="pokemonCard rounded p-2 cursor-pointer" id="${pokemonInfo.data.order}" style="background: linear-gradient(var(--whitePrimary), var(--whiteSecondary)); width: 48%; height: 70%">
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
              pokemonList.innerHTML += content;




            };


          })
      })

    });

  // SEARCHBAR EVENT - Hide cards that don't match user's input
  const pokemonInput = this.document.getElementById("pokemonInput");

  pokemonInput.addEventListener("keyup", function () {
    const listChildren = Array.from(pokemonList.children);

    listChildren.forEach(pokemon => {

      pokemon.classList.remove("d-none");

      if (!pokemon.outerText.includes(pokemonInput.value.toUpperCase())) {
        pokemon.classList.add("d-none");
      }
    })

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
          src="https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/other/dream-world/1.svg"
          alt="Bulbasaur" />

        <ul class="list-unstyled">
          <ul class="list-group list-group-horizontal">
            <li class="list-group-item py-0 px-1" style="background-color:#7AC74C">grass</li>
            <li class="list-group-item py-0 px-1" style="background-color:#A33EA1">poison</li>
          </ul>
          <li><i class="fa-solid fa-hand-fist"></i> Special atk: 65</li>
          <li><i class="fa-solid fa-shield-halved"></i> Special def: 65</li>
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
      <input type="text" id="pokemonInput" class="col-12 rounded"
        placeholder="Insira o nome do pok??mon para pesquisar. Ex: Pikachu">
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
