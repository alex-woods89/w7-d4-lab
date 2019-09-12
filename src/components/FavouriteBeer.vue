<template>
  <div>
    <button v-on:click="handleClick">Mark as Favourite</button>
    <li>{{favouriteBeer.name}}</li>
  </div>
</template>

<script>

import {eventBus} from '../main'

export default {
    name: "favourite-beer",
    props: ["beer"],
    methods: {
        handleClick() {
            eventBus.$emit('beer-favourited', this.favouriteBeer);
        },
    }
}
</script>

<style lang="stylus">

</style>