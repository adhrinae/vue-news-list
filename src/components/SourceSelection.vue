<template>
  <div class="sourceselection">
    <div class="jumbotron">
      <h2><span class="glyphicon glyphicon-list-alt"></span>News List</h2>
      <h4>Select News Source</h4>
      <select class="form-control" v-on:change="sourceChanged">
        <option value="">Please select news source</option>
        <option v-bind:value="source.id" v-for="source in sources">
          {{ source.name }}
        </option>
      </select>

      <div v-if="source">
        <h6>{{ source.description }}</h6>
        <a v-bind:href="source.url" class="btn btn-primary" target="_blank">
          Go To {{ source.name }} Website
        </a>
      </div>
    </div>
  </div>

</template>

<script>
  export default {
    name: 'sourceselection',
    data () {
      return {
        sources: [],
        source: ''
      }
    },

    methods: {
      sourceChanged (e) {
        for (let source of this.sources) {
          if (source.id === e.target.value) {
            this.source = source
          }
        }

        this.$emit('sourceChanged', e.target.value)
      }
    },

    created () {
      this.$http.get('https://newsapi.org/v1/sources?language=en')
        .then(response => {
          this.sources = response.data.sources
        })
    }
  }
</script>

<style scoped>
  
</style>
