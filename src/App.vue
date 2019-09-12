<template>
  <div id="app">
   
  
  </div>
</template>

<script>
  import BeerList from './components/BeerList'
  import BeerDetail from './components/BeerDetail'

export default {
  data(){
    return {
      beers: [],
      selectedBeer: null
    }
  },
  components: {
    "beer-list": BeerList,
    "beer-detail": BeerDetail
  },
  mounted(){
    fetch('https://api.punkapi.com/v2/beers')
    .then(result => result.json())
    .then(beers => this.beers = beers)
  }
}
</script>

<style lang="css">
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
