<template lang="html">

<li v-on:click="clickOnCountry">{{ country.name }} img src = {{ country.flag }} </li>
</template>

<script>
import { eventBus } from '../main.js'

export default {
  name: 'list-component',
  props: ['country', 'index'],
  methods: {
    clickOnCountry(){
      // console.log('this country has been clicked:', this.country.name);
      eventBus.$emit('selected-country', this.country)
      // Giving to
    }
  }
}
</script>

<style lang="css" scoped>
</style>

<!-- Allows absorbing from parent component. -->
