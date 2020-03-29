<template>
    <div class="joke">
        <div class="navi">
            <button class="button" type="button" name="button" @click="charmander()"> Charmander </button>
            <button class="button" type="button" name="button" @click="pikachu()"> Pikachu </button>
            <button class="button" type="button" name="button" @click="bulbasaur()"> Bulbasaur </button><br>
            <button class="button" type="button" name="button" @click="squirtle()"> Charmander </button>
            <button class="button" type="button" name="button" @click="caterpie()"> Caterpie </button>
            <button class="button" type="button" name="button" @click="weedle()"> Weedle </button>
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
    charmander: function () {
        axios.get('https://pokeapi.co/api/v2/pokemon/')
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
    }
    }
}

</script>

<style></style>