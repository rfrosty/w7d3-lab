<template lang="html">
  <div class="">
    <h1>Country's lab</h1>
    <countries-list :countries='countries'></countries-list>
  </div>

</template>

<script>

import CountriesList from './components/CountriesList.vue'

export default {
  name: 'app',
  data () {
    return {
      countries: []
    }
  },
  mounted () {
    fetch('https://restcountries.eu/rest/v2/all')
    .then(response => response.json())
    .then(data => this.countries = data )
  },

components: {
  "countries-list": CountriesList,
}
}
</script>

<style lang="css" scoped>
</style>

<!-- mounted is a lifecycle hook: it just happens. -->
<!-- this was reffering to default. -->
