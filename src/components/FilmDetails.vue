<template lang="html">
  <div v-if="film" class="filminfo">
    <h1>{{ film.title }}</h1>
    <p>Director: {{ film.director }}</p>
    <p>Description: {{ film.description }}</p>

    <div v-if="findPic" class="movie-pic">
      <img :src="findPic" :alt="film.title">
    </div>


  </div>
</template>

<script>
export default {
  name: 'film-details',
  props: ['film'],
  data(){
    return {
      filmpics: [{name: "Castle in the Sky", url:'https://lumiere-a.akamaihd.net/v1/images/open-uri20150422-12561-1vkk9t3_d3955dad.jpeg?region=0%2C0%2C1000%2C1388&optimize=true'},
    {name: "Grave of the Fireflies", url: "https://m.media-amazon.com/images/M/MV5BZjEwNDVhZjMtYzA1MS00ZWUxLThjOGUtZTliNGZiNGYyMjA3XkEyXkFqcGdeQXVyNjU0OTQ0OTY@._V1_.jpg"},
    {name: "My Neighbor Totoro", url: "https://lumiere-a.akamaihd.net/v1/images/open-uri20150422-12561-yutq1u_10dca429.jpeg?region=0%2C0%2C1000%2C1328&optimize=true"},
    {name: "Kiki's Delivery Service", url: "https://i.pinimg.com/originals/9d/5c/b0/9d5cb00ea0a430bb2c537b83f5df88cc.jpg"},
    {name: "Only Yesterday", url: "http://3.bp.blogspot.com/-iOCWKv7AKkY/U8ODeYU-1rI/AAAAAAAAAoU/HUCgxkEUkW8/s1600/only+yesterday+poster.jpg"},
    {name: "Porco Rosso", url: "https://i.pinimg.com/originals/36/61/f6/3661f6300e0b67a59534513a3dc209ea.jpg"},
    {name: "Pom Poko", url: "https://fanart.tv/fanart/movies/15283/movieposter/pom-poko-568aee842448a.jpg"},
    {name: "Whisper of the Heart", url: "https://cdn.shoplightspeed.com/shops/608693/files/5908490/studio-ghibli-gkids-whisper-of-the-heart-dvd-gkids.jpg"},
    {name: "Princess Mononoke", url: "https://www.mauvais-genres.com/19098/princess-mononoke-movie-poster-15x21-in-1997-hayao-miyazaki-studio-ghibli.jpg"},
    {name: "My Neighbors the Yamadas", url: "https://vignette.wikia.nocookie.net/dubbing9585/images/f/fa/My-neighbors-the-yamadas-poster.jpg/revision/latest?cb=20171223052252"},
    {name: "Spirited Away", url: "https://d1w8cc2yygc27j.cloudfront.net/-7994744733288836437/658245118940726818.jpg"},
    {name: "The Cat Returns", url: "https://cdn.shoplightspeed.com/shops/608693/files/1921089/studio-ghibli-gkids-cat-returnsthe-blu-ray-dvd.jpg"},
    {name: "Howl's Moving Castle", url: "https://static.shoplightspeed.com/shops/608693/files/005917230/studio-ghibli-gkids-howls-moving-castle-dvd-gkids.jpg"},
    {name: "Tales from Earthsea", url: "http://salc.kmutt.ac.th/file/Cover/VCD/SALC_1190711702.jpg"},
    {name: "Ponyo", url: "https://fesapusewebsite.blob.core.windows.net/fathom/ponyo-1000x1480-r2-3c7dd4adc4c5119cdacef777caf4657a.jpg"},
    {name: "Arrietty", url: "https://lumiere-a.akamaihd.net/v1/images/b86153c13d8c91273ec53e183b9ebd537cf33434_81416e81.jpeg?region=0%2C0%2C750%2C1095&optimize=true"},
    {name: "From Up on Poppy Hill", url: "https://images-na.ssl-images-amazon.com/images/I/81JVKziDNAL._SL1500_.jpg"},
    {name: "The Wind Rises", url: "https://samuelrookeblog.files.wordpress.com/2018/07/23rises.jpg"},
    {name: "The Tale of the Princess Kaguya", url: "https://image.tmdb.org/t/p/original/cQidJuA546OSSXKWXoiCeINDxuj.jpg"},
    {name: "When Marnie Was There", url: "https://i.pinimg.com/originals/85/f3/ed/85f3ed391c08bfff6d5d2905f23f25e6.jpg"},







  ],

    }
  },
  computed: {
    findPic: function() {
      for (var filmpic of this.filmpics) {
        if (filmpic.name === this.film.title) {
          return filmpic.url
        }
      }
    }
  }
}
</script>

<style lang="css" scoped>
.movie-pic img{


  height: 55vh;
  width: 40vh;
}
/* .filminfo {
  font-family: 'Roboto', sans-serif;
  grid-column-start: 1;
  grid-column-end: 7;
  grid-row-start: 1;
  grid-row-end: 5;
  box-sizing: border-box;
  padding-left: 10px;
} */

/* .filminfo h1 p {
  grid-column-start: 1;
  grid-column-end: 5;
  grid-row-start: 1;
  grid-row-end: 3;
} */


</style>
