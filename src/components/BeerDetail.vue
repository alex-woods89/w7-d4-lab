<template>
    <article v-if="beer">  
     <h3>{{beer.name}}</h3>
     <div>
         <p>Name: {{beer.name}}</p>
         <p>abv: {{beer.abv}}</p>
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