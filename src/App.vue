<template>
  <div id="app">
   <h1>Beer App!</h1>
    <beer-list :beers="beers"></beer-list>
    <beer-detail :beer="selectedBeer"></beer-detail> 
    <favourite-beer :beer="selectedBeer"> </favourite-beer>
  </div>
</template>

<script>
  import BeerList from './components/BeerList'
  import BeerDetail from './components/BeerDetail'
  import FavouriteBeer from './components/FavouriteBeer'
  import {eventBus} from './main'

export default {
  data(){
    return {
      beers: [],
      selectedBeer: null,
      favouriteBeers: []
    }
  },
  components: {
    "beer-list": BeerList,
    "beer-detail": BeerDetail,
    "favourite-beer": FavouriteBeer
  },
  mounted(){
    fetch('https://api.punkapi.com/v2/beers')
    .then(result => result.json())
    .then(beers => this.beers = beers)

    eventBus.$on('beer-selected', (beer) => {
    this.selectedBeer = beer}),

    eventBus.$on('beer-favourited', (beer) => {
      this.favouriteBeers.push(selectedBeer)
    })
  
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
