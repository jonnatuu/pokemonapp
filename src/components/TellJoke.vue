<template>
    <div class="joke">
        <div class="form-inline justify-content-center mt-4 mb-1">
                  <input type="text" v-model="nimi" class="form-control" placeholder="Anna pokemonin nimi" >
                  <button v-on:click="search" type="submit" class="btn btn-light ml-1 text-black">Search</button>  
        </div>
        <div class="kuvat">
            <h4>Nimi: {{ nimi }}</h4>
            <h4>Pokedex number: {{ url }}</h4>
            <img :src="img" alt="" />
        </div>
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
  methods: {
    search: function () {
        axios.get(`https://pokeapi.co/api/v2/pokemon/${this.nimi}`)
        .then(response => {
        this.img = response.data.sprites.front_default;
        this.nimi = response.data.name;
        this.url =response.data.id;
        })
    },
    /* pikachu: function () {
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
    squirtle: function () {
        axios.get('https://pokeapi.co/api/v2/pokemon/squirtle/')
        .then(response => {
        this.img = response.data.sprites.front_default;
        this.nimi = response.data.name;
        this.url =response.data.id;
    })
    },
    caterpie: function () {
        axios.get('https://pokeapi.co/api/v2/pokemon/caterpie/')
        .then(response => {
        this.img = response.data.sprites.front_default;
        this.nimi = response.data.name;
        this.url =response.data.id;
        })
    },
    weedle: function () {
        axios.get('https://pokeapi.co/api/v2/pokemon/weedle/')
        .then(response => {
        this.img = response.data.sprites.front_default;
        this.nimi = response.data.name;
        this.url =response.data.id;
        })
    } */
    }
}

</script>

<style></style>