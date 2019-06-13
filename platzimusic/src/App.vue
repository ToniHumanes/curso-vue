<template>
  <div id="app">
    <img src="./assets/logo.png">
    <h1>PlatziMusic</h1>
    <select v-model="selectedCountry">
      <option v-for="country in countries" v-bind:value="country.value">{{country.name}}</option>
    </select>
    <Spinner v-show="loading"> </Spinner>
    <ul>
      <artist
        v-for="artist in artists"
        v-bind:artist="artist"
        v-bind:key="artist.mdid"
      ></artist>
    </ul>
  </div>
</template>

<script>
import Artist from './components/Artist.vue'
import Spinner from './components/Spinner.vue'
import getArtists from './api'
export default {
  name: 'app',
  data () {
    return {
      artists: [],
      countries: [
        {name: 'Argentina', value: 'argentina', id: 1},
        {name: 'España', value: 'spain', id: 2},
        {name: 'Colombia', value: 'colombia', id: 3}
      ],
      selectedCountry: 'argentina',
      loading: true
    }
  },
  components:{
    Artist: Artist,
    Spinner: Spinner
  },
  methods:{
    refreshArtists(){
    const self = this
    this.loading = true
    getArtists(this.selectedCountry)
    .then( function(artists){
      self.loading = false;
      self.artists = artists
      })
    }
  },
  mounted(){
    this.refreshArtists();
  },
  watch: {
    selectedCountry(){
      this.refreshArtists();
    }
  }
}
</script>

<style scoped>
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

h1,
h2 {
  font-weight: normal;
}

ul {
  list-style-type: none;
  padding: 0;
}

li {
  display: inline-block;
  margin: 0 10px;
}

a {
  color: red;
}

.artists h2 {
  display: flex;
  flex-direction: column;
  align-items: center;
}
</style>
