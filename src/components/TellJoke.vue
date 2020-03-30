<template>
    <div class="joke">
        <div class="form-inline justify-content-center mt-4 mb-1">
        <!-- Search Pokemons -->
        <h4> Voit etsiä haluamaasi Pokemonia tästä: </h4>
                  <input type="text" v-model="nimi" class="form-control" placeholder="Anna pokemonin nimi" >
                  <button v-on:click="search" type="submit" class="btn btn-light ml-1 text-black"> Etsi </button>  
        </div>
        <!-- Results of search -->
        <div class="kuvat">
            <h4>Nimi: {{ nimi }}</h4>
            <h4>Pokedex number: {{ url }}</h4>
            <img :src="img" alt="" />
        </div>
        <h4> Tai voit valita valmiiksi tästä: </h4>
            <button class="button" type="button" name="button" @click="charmander()"> Charmander </button>
            <button class="button" type="button" name="button" @click="pikachu()"> Pikachu </button>
            <button class="button" type="button" name="button" @click="bulbasaur()"> Bulbasaur </button><br>
    </div>
</template>

<script>
import axios from 'axios';

export default {
  name: 'Pokemons',
  data: function() {
      return{
        img: '',
        nimi: '',
        url: ''
      }
      },
      // search data from pokeapi
  methods: {
    search: function () {
        axios.get(`https://pokeapi.co/api/v2/pokemon/${this.nimi}`)
        .then(response => {
        this.img = response.data.sprites.front_default;
        this.nimi = response.data.name;
        this.url =response.data.id;
        })
    },
        charmander: function () {
        axios.get('https://pokeapi.co/api/v2/pokemon/charmander')
        .then(response => {
        this.img = response.data.sprites.front_default;
        this.nimi = response.data.name;
        this.url =response.data.id;
        })
    },
    pikachu: function () {
        axios.get('https://pokeapi.co/api/v2/pokemon/pikachu/')
        .then(response => {
        this.img = response.data.sprites.front_default;
        this.nimi = response.data.name;
        this.url =response.data.id;
        })
    },
    bulbasaur: function () {
        axios.get('https://pokeapi.co/api/v2/pokemon/bulbasaur/')
        .then(response => {
        this.img = response.data.sprites.front_default;
        this.nimi = response.data.name;
        this.url =response.data.id;
        })
    },
    }
}

</script>

<style></style>