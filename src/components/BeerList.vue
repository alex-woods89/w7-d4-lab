<template lang="html">
    <select v-on:change="handleChange" v-model="selectedBeer">
        <option v-for="beer in beers" :value="beer">{{beer.name}}</option>
    </select>    
</template>


<script>
   import { eventBus } from '../main'

export default {
     name: "beer-list",
     data() {
         return {
             "selectedBeer": {}
         }
     },
     props: ["beers"],
     methods: {
         handleChange() {
             eventBus.$emit('beer-selected', this.selectedBeer)
         }
     }
}
</script>

<style lang="stylus">

</style>