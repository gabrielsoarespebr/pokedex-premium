<script setup>

// import axios from 'axios';
// defineProps({
//   msg: {
//     type: String,
//     required: true
//   }
// })

// let pokemons;

// axios
//   .get("https://pokeapi.co/api/v2/pokemon?limit=100000&offset=0")
//   .then((response) => {
//     pokemons = response.data;
//     console.log(pokemons);
//   })

//   const pokemonList = document.getElementById("pokemonList");
//   console.log(pokemonList);

</script>

<template>
  <main class="d-flex justify-content-around">
    <div id="pokemonPreview" class="col-4 bg-white rounded p-3">
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
      <input type="text" id="inputPokemon" class="col-12 rounded" placeholder="Insira o nome do pokémon para pesquisar. Ex: Pikachu">
      <div id="pokemonList" class="d-flex justify-content-flex flex-wrap gap-1 mt-1">

        <div class="pokemonCard col rounded p-2">
          <div class="d-flex align-items-center justify-content-between">
            <h2 class="m-0 h6">Bulbasaur</h2>
            <p class="m-0 fs-6">#1</p>
          </div>

          <div class="d-flex align-items-center justify-content-around">
            <img class="col-5"
              src="https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/other/official-artwork/1.png"
              alt="Bulbasaur" />
            <ul class="list-group text-center">
              <li class="list-group-item py-0 px-1 bg-success font-small">GRASS</li>
              <li class="list-group-item py-0 px-1 bg-danger font-small">POISON</li>
            </ul>
          </div>

        </div>

        <div class="pokemonCard col rounded p-2">
          <div class="d-flex align-items-center justify-content-between">
            <h2 class="m-0 h6">Bulbasaur</h2>
            <p class="m-0 fs-6">#1</p>
          </div>

          <div class="d-flex align-items-center justify-content-around">
            <img class="col-5"
              src="https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/other/official-artwork/1.png"
              alt="Bulbasaur" />
            <ul class="list-group text-center">
              <li class="list-group-item py-0 px-1 bg-success font-small">GRASS</li>
              <li class="list-group-item py-0 px-1 bg-danger font-small">POISON</li>
            </ul>
          </div>

        </div>

        
        <div class="pokemonCard col rounded p-2">
          <div class="d-flex align-items-center justify-content-between">
            <h2 class="m-0 h6">Bulbasaur</h2>
            <p class="m-0 fs-6">#1</p>
          </div>

          <div class="d-flex align-items-center justify-content-around">
            <img class="col-5"
              src="https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/other/official-artwork/1.png"
              alt="Bulbasaur" />
            <ul class="list-group text-center">
              <li class="list-group-item py-0 px-1 bg-success font-small">GRASS</li>
              <li class="list-group-item py-0 px-1 bg-danger font-small">POISON</li>
            </ul>
          </div>

        </div>

        
        <div class="pokemonCard col rounded p-2">
          <div class="d-flex align-items-center justify-content-between">
            <h2 class="m-0 h6">Bulbasaur</h2>
            <p class="m-0 fs-6">#1</p>
          </div>

          <div class="d-flex align-items-center justify-content-around">
            <img class="col-5"
              src="https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/other/official-artwork/1.png"
              alt="Bulbasaur" />
            <ul class="list-group text-center">
              <li class="list-group-item py-0 px-1 bg-success font-small">GRASS</li>
              <li class="list-group-item py-0 px-1 bg-danger font-small">POISON</li>
            </ul>
          </div>

        </div>

        
        <div class="pokemonCard col rounded p-2">
          <div class="d-flex align-items-center justify-content-between">
            <h2 class="m-0 h6">Bulbasaur</h2>
            <p class="m-0 fs-6">#1</p>
          </div>

          <div class="d-flex align-items-center justify-content-around">
            <img class="col-5"
              src="https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/other/official-artwork/1.png"
              alt="Bulbasaur" />
            <ul class="list-group text-center">
              <li class="list-group-item py-0 px-1 bg-success font-small">GRASS</li>
              <li class="list-group-item py-0 px-1 bg-danger font-small">POISON</li>
            </ul>
          </div>

        </div>

        
        <div class="pokemonCard col rounded p-2">
          <div class="d-flex align-items-center justify-content-between">
            <h2 class="m-0 h6">Bulbasaur</h2>
            <p class="m-0 fs-6">#1</p>
          </div>

          <div class="d-flex align-items-center justify-content-around">
            <img class="col-5"
              src="https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/other/official-artwork/1.png"
              alt="Bulbasaur" />
            <ul class="list-group text-center">
              <li class="list-group-item py-0 px-1 bg-success font-small">GRASS</li>
              <li class="list-group-item py-0 px-1 bg-danger font-small">POISON</li>
            </ul>
          </div>

        </div>

        
        <div class="pokemonCard col rounded p-2">
          <div class="d-flex align-items-center justify-content-between">
            <h2 class="m-0 h6">Bulbasaur</h2>
            <p class="m-0 fs-6">#1</p>
          </div>

          <div class="d-flex align-items-center justify-content-around">
            <img class="col-5"
              src="https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/other/official-artwork/1.png"
              alt="Bulbasaur" />
            <ul class="list-group text-center">
              <li class="list-group-item py-0 px-1 bg-success font-small">GRASS</li>
              <li class="list-group-item py-0 px-1 bg-danger font-small">POISON</li>
            </ul>
          </div>

        </div>

        
        <div class="pokemonCard col rounded p-2">
          <div class="d-flex align-items-center justify-content-between">
            <h2 class="m-0 h6">Bulbasaur</h2>
            <p class="m-0 fs-6">#1</p>
          </div>

          <div class="d-flex align-items-center justify-content-around">
            <img class="col-5"
              src="https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/other/official-artwork/1.png"
              alt="Bulbasaur" />
            <ul class="list-group text-center">
              <li class="list-group-item py-0 px-1 bg-success font-small">GRASS</li>
              <li class="list-group-item py-0 px-1 bg-danger font-small">POISON</li>
            </ul>
          </div>

        </div>

      </div>
    </div>

  </main>
</template>

<style scoped>
main {
  color: var(--darkBluePrimary);
}

#pokemonPreview,
.pokemonCard {
  background: linear-gradient(var(--whitePrimary), var(--whiteSecondary));
}

.font-small{
  font-size: 60%;
}
</style>
