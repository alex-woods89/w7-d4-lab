<template>
  <div>
    <button v-on:click="handleClick">Mark as Favourite</button>
    <li></li>
  </div>
</template>

<script>

import {eventBus} from '../main'

export default {
    name: "favourite-beer",
    methods: {
        handleClick() {
            eventBus.$emit('beer-favourited', this.favouriteBeer);
        },
    }
}
</script>

<style lang="stylus">

</style>