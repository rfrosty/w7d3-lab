<template lang="html">
<div class="">
  <ul>
    <list-component v-for="(country, index) in countriesproperty" :country="country" :index="index"></list-component>
  </ul>
</div>
</template>

<script>

import ListComponent from './ListComponent.vue'

export default {
  name: 'countries-list',

  props: ['countriesproperty'],

  components: {
    "list-component": ListComponent
  }

}
</script>

<style lang="css" scoped>
</style>
