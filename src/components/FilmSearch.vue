<template lang="html">
  <div class="select">
    <label for="filmSelector">Select a Film</label>
    <select v-on:change="nowSelected" v-model="selectedFilmIndex" id="filmSelector">
      <option disabled value="">Film</option>
      <option v-for="(film, index) in films" :value="index">{{ film.title }}</option>
    </select>
  </div>
</template>

<script>
import { eventBus } from '../main.js'

export default {
  name: 'selected-film',
  data(){
    return {
      selectedFilmIndex: ''
    }
  },
  props: ['films'],
  methods: {
    nowSelected: function(){
      eventBus.$emit('selected-film', this.selectedFilmIndex)
    }
  }
}
</script>

<style lang="css" scoped>
.select select{
  font-family: 'Roboto', sans-serif;
  height: 25px;
  font-size: 12px;
  margin-top: 10px;
}

.select {
  height: 50px;
}


</style>
