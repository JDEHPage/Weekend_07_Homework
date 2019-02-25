<template lang="html">
  <div class="">
    <label for="infoSelector">Select a Info</label>
    <select v-on:change="nowSelected" v-model="selectedInfoIndex" id="infoSelector">
      <option disabled value="">Info</option>
      <option :value="info">{{ info }}</option>
      <option v-for="(info, index) in filminfo" :value="info">{{ info }}</option>
      <option v-for="(info, index) in filminfo" :value="info">{{ info }}</option>

    </select>
  </div>
</template>

<script>
import { eventBus } from '../main.js'

export default {
  name: 'selected-info',
  data(){
    return {
      selectedInfoIndex: ''
    }
  },
  props: ['filminfo'],
  methods: {
    nowSelected: function(){
      eventBus.$emit('selected-info', this.selectedInfoIndex)
    }
  },
  // computed: {
  //   infoOptions: function() {
  //     for (var info of this.filminfo) {
  //       debugger
  //       if (info.isArray) {
  //         return
  //       }
  //     }
  //   }
  // }
}
</script>

<style lang="css" scoped>
</style>
