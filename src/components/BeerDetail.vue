<template>
    <article v-if="beer">  
     <h3>{{beer.name}}</h3>
     <div>
         <p>ABV: {{beer.abv}}%</p>
         <img :src="beer.image_url"  height="300">
         <p>{{beer.description}}</p>
         
     </div>
    </article>
</template>

<script>
  import FavouriteBeer from './FavouriteBeer'
  import {eventBus} from '../main'
export default {
    name: "beer-detail",
    props: ["beer"],

components:{
    "favourite-beer": FavouriteBeer,
}
}

</script>

<style lang="stylus">
</style>