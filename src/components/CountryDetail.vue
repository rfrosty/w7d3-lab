<template lang="html">
  <div v-if="country">
    <h1>{{country.name}}</h1>
    <p>{{country.capital}}</p>
    <p>{{country.population}}</p>
  </div>

</template>

<script>
export default {
  name: 'country-detail',
  props: ['country']
}
</script>

<style lang="css" scoped>
</style>
