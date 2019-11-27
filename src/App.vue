<template lang="html">
  <div class="">
    <h1>Country's lab</h1>
    <country-detail :country='selectedCountry'></country-detail>
    <countries-list v-bind:countriesproperty='countries'></countries-list>
  </div>

</template>

<script>

import { eventBus } from './main.js'
import CountriesList from './components/CountriesList.vue'
import CountryDetail from './components/CountryDetail.vue'

export default {
  name: 'app',

  data () {
    return {
      countries: [],
      selectedCountry: null
    }
  },

  mounted () {
    fetch('https://restcountries.eu/rest/v2/all')
    .then(response => response.json())
    .then(data => this.countries = data )

    eventBus.$on('selected-country', (country) => {
      this.selectedCountry = country;
    })
  },

  components: {
    "countries-list": CountriesList,
    "country-detail": CountryDetail
  }
}
</script>

<style lang="css" scoped>
</style>

<!-- the file in fetch is .JSON -->
<!-- mounted is a lifecycle hook: it just happens. -->
<!-- this was reffering to default. -->
