<template lang="html">
  <div class="container">
    <div class="nav">
      <h2>Studio Ghbili Films</h2>
      <film-select :films="films"></film-select>
    </div>
    <div class="content">
      <film-details :film="selectfilm"></film-details>
    </div>
    <div class="characters">
      <!-- <info-select :filminfo="selectfilm"></info-select> -->
      <info-details :filminfo="selectfilm"></info-details>
    </div>


    </div>
</template>

<script>
import { eventBus } from './main.js'
import FilmSearch from './components/FilmSearch.vue'
import FilmDetails from './components/FilmDetails.vue'
// import InfoSelelct from './components/InfoSelect.vue'
import InfoDetails from './components/InfoDetails.vue'

export default {
  data(){
    return {
      films: [],
      selectfilm: null,
    }
  },
  mounted(){
    fetch('https://ghibliapi.herokuapp.com/films/')
    .then(res => res.json())
    .then(films => this.films = films)

    eventBus.$on('selected-film', (index) => {
      this.selectfilm = this.films[index]
    })

    // eventBus.$on('selected-info', (info) => {
    //   this.selectinfo = info
    // })


  },
  components: {
    'film-select': FilmSearch,
    'film-details': FilmDetails,
    // 'info-select': InfoSelelct
    'info-details': InfoDetails

  },
  methods: {

  }
}
</script>
<style lang="css" scoped>



.container {
 background-color: rgba(227,235,242,0.1);
 display: grid;
 grid-template-columns: 230px 150px 150px 20% 20% 20%;
 grid-template-rows: 20% 20% 20% 20% 20% 20%;
 height: 100vh;

}

.nav {
  font-family: 'Roboto', sans-serif;
  background-color: #FFD1BA;
  grid-column-start: 1;
  grid-column-end: 2;
  grid-row-start: 1;
  grid-row-end: 6;
  box-sizing: border-box;
  padding-left: 8px;
  height: 96vh;
  background-image: url(./assets/ghiblilogonew.png);
  background-repeat: no-repeat;
  background-position: bottom;
  background-size: contain;

}

.content {
  font-family: 'Roboto', sans-serif;
  grid-column-start: 2;
  grid-column-end: 6;
  grid-row-start: 1;
  grid-row-end: 5;
  box-sizing: border-box;
  padding-left: 10px;
   height: 100vh;

   /* display: inline-grid;
   grid-template-columns:  25% 25% 25% 25%;
   grid-template-rows:  25% 25% 25% 25%; */



}

.characters {
  font-family: 'Roboto', sans-serif;
  grid-column-start: 4;
  grid-column-end: 6;
  grid-row-start: 3;
  grid-row-end: 5;
  box-sizing: border-box;
  padding-left: 10px;

  display: flex;
}

</style>
