<template>
  <div class="container" id="app">
    <SourceSelection v-on:sourceChanged="sourceChanged"></SourceSelection>
    <Newslist v-bind:source="source"></Newslist>
  </div>
</template>

<script>
import SourceSelection from './components/SourceSelection'
import Newslist from './components/Newslist'

export default {
  name: 'app',
  components: {
    SourceSelection,
    Newslist
  },
  data () {
    return {
      source: ''
    }
  },
  methods: {
    sourceChanged (source) {
      this.source = source
    }
  }
}
</script>

<style>
#app {
  padding-top: 20px;
}
</style>
