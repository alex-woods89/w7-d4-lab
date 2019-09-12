<template>
    <article v-if="beer">  
     <h3>{{beer.name}}</h3>
     <div>
         <p>Name: {{beer.name}}</p>
         <p>ABV: {{beer.abv}}%</p>
         <img :src="beer.image_url"  height="300">
         <p>{{beer.description}}</p>
         <favourite-beer></favourite-beer>
     </div>
    </article>
</template>

<script>

import {eventBus} from '../main'

export default {
    name: "beer-detail",
    props: ["beer"]
}
</script>

<style lang="stylus">

</style>