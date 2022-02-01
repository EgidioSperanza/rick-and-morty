<template>
  <div id="app">
    <header>
      <h1>Rick and Morty App</h1>
      <search-bar @search="filterResults" @reset="resetResult"/>
    </header>
    <loader v-if="!isLoaded" />
    <main-container v-else :personages="personagesFiltered" />
  </div>
</template>

<script>
import SearchBar from './components/SearchBar.vue'
import MainContainer from './components/MainContainer.vue'
import Loader from './components/Loader.vue'
import axios from 'axios'
export default {
  name: 'App',
  components: {
    SearchBar,
    MainContainer,
    Loader,
  },
  data() {
    return {
      personages: [],
      personagesFiltered: [],
      isLoaded: false,
    }
  },
  mounted() {
    axios
      .get('https://api.sampleapis.com/rickandmorty/characters')
      .then((response) => {
        this.personages = response.data
        this.personagesFiltered = response.data
        this.isLoaded = true
      })
  },
  methods: {
    filterResults(keyword) {
      this.personagesFiltered = this.personages.filter((personage) =>{
        return personage.name.toLowerCase().includes(keyword);
      })
    },
    resetResult() {
      return this.personagesFiltered=this.personages;
      
    }
  },
}
</script>

<style lang="scss">
@import './style/main.scss';
header {
  width: 80%;
  margin: 0 auto;
  text-align: center;
  padding: 20px 0;
}
</style>
