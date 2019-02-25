<template lang="html">
  <div v-if="this.selectinfo.length > 0" class="charactersinfo">
    <p>Characters:</p>
    <ul>
      <li v-for="info of selectinfo">{{ info.name }}</li>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'info-details',
  props: ['filminfo'],
  data(){
    return {
      selectinfo: null,
    }
  },

  watch: {
  filminfo: function(newVal, oldVal) { if (newVal) {
    fetch("https://ghibliapi.herokuapp.com/people/")
    .then(res => res.json())
    .then(info => {
        // const people = info.filter(person => this.filminfo.url === person.films[0])
        // debugger
        this.selectinfo = info.filter(person => this.filminfo.url === person.films[0])

    })

  }
  }
}



  }


</script>

<style lang="css" scoped>


/* .charactersinfo {
  font-family: 'Roboto', sans-serif;
  grid-column-start: 3;
  grid-column-end: 4;
  grid-row-start: 4;
  grid-row-end: 5;
  box-sizing: border-box;
  padding-left: 10px;
} */

</style>
