<template>
  <div id='content-search' class='ContentSearch'>
      <input class='InputSearch' placeholder='Busque um filme por nome, ano ou gênero...' v-on:change='searchName' />
      <section class='CardSearched' v-for='(item, index) in items' :key='index'>
          <div class='PoserCard'>
              <div class='backgroundCard' :style="{'background-image': 'url(' + 'https://image.tmdb.org/t/p/w500/'+ item.poster_path +')'}"></div>
          </div>
          <div class='DescriptionCard'>
              <div class='TitleCard'><span>{{item.title}}</span><span>{{Math.round(item.vote_average/0.1)}}%</span></div>
              <div class='SynopsisCard'>
                  <div class='dateRelease'>{{item.release_date}}</div>
                  <div class='synopsisMovie'>{{item.overview}}
                  </div>
                  <div className='categoriesMovie'>
                          <li v-for='(categ, index) in item.genre_ids' :key='index' v-on:change='searchGenres(categ)'>{{msg}}</li>
                  </div>
              </div>
          </div>
      </section>
      <!-- <Pagination>
          {numberPagination()}  
      </Pagination> -->
  </div>
</template>

<script>

export default{
  el: '#content-search',
  props: {
    msg: String
  },
  data() {
    return {
      items: {}
    }
  },
  beforeMount(){
    this.getName();
  },
  methods: {
    async getName(){
      const res = await fetch('https://api.themoviedb.org/3/discover/movie?api_key=6d27b243520c3d8bd2325f2289b0cf7d&language=pt-BR&sort_by=popularity.desc&include_adult=false&include_video=false&page=1&primary_release_year=2021&with_watch_monetization_types=flatrate');
      const data = await res.json();
      this.items = data.results;
    },

    async searchName(e) {
      const res = await fetch('https://api.themoviedb.org/3/search/movie?api_key=6d27b243520c3d8bd2325f2289b0cf7d&language=pt-BR&query='+e.target.value+'&page=1&include_adult=false');
      const data = await res.json();
      console.log(data);
      if (data.results !== undefined) {
        this.items = data.results;
      }
    },
    searchGenres(e) {
      console.log(e)
    }
  }
};

</script>

<style>
  .ContentSearch {
    flex: 1;
    position: relative;
    background: #fff;
    color: #000;
    max-width: 1024px;
    width: 100%;
    margin: 0px auto;
    padding: 50px;
    height: 100%;
    box-sizing: border-box;
  }

  .InputSearch {
    background: #ebebeb;
    position: relative;
    width: 100%;
    border: 1px solid transparent;
    border-radius: 20px;
    color: #116193;
    padding: 10px 20px;
    box-sizing: border-box;
    font-family: 'Abel', sans-serif;
    font-size: 18px;
    outline: none;
    transition: .25s ease-in-out;
  }

  .InputSearch:hover {
    border-color: #fff;
    box-shadow: 0 3px 15px rgba(17, 97, 147, .35);
  }

  .InputSearch::placeholder {
    color: #91b2c7;
  }

  .CardSearched {
    width: 100%;
    height: 308px;
    /* background: ${props => props.theme.fg}; */
    margin-top: 50px;
    display: flex;
    cursor: pointer;
    transition: .25s ease-in-out;
    animation: animeCard .24s;
    border: 1px solid transparent;
    border-radius: 8px;
    overflow: hidden;

    @keyframes animeCard {
      from {
        transform: scale(.95);
        opacity: .5;
      }

      to {
        transform: scale(1);
        opacity: 1;
      }
    }
  }

  .CardSearched:hover {
    box-shadow: 0 5px 15px rgba(17, 97, 147, .35);
    border-color: #fff;
  }

  .PoserCard {
    width: 205px;
    height: 308px;
    overflow: hidden;
  }

  .backgroundCard {
    /* background: transparent; */
    background-image: repeating-linear-gradient(red, yellow 10%, green 20%);
    background-repeat: no-repeat;
    background-size: cover;
    position: relative;
    width: 100%;
    height: 100%;
    transition: .4s ease-in-out;
    cursor: pointer;

    /* ${CardSearched}:hover & {
      transform: scale(1.05);
    } */
  }

  .DescriptionCard {
    background: #ebebeb;
    width: 78%;
    height: 100%;
    overflow: hidden;
  }

  .TitleCard {
    position: relative;
    height: 20%;
    background: #116193;
    color: #00e8e4;
    font-family: 'Abel', sans-serif;
    line-height: 50px;
  }

  .TitleCard span {
    position: absolute;
    bottom: 5px;
    left: 100px;
    width: fit-content;
    height: fit-content;
    font-size: 35px;
  }

  .TitleCard span:last-child{
    position: absolute;
    width: 75px;
    height: 75px;
    bottom: -38px;;
    left: 2.5%;
    transform: translateX(-4%);
    background: #116193;
    border-radius: 50%;
    color: #00e8e4;
    text-align: center;
    line-height: 75px;
    font-size: 24px;
  }

  .TitleCard span:last-child:after {
    content: '';
    position: absolute;
    width: 82.5%;
    height: 82.5%;
    left: 50%;
    top: 50%;
    transform: translate(-50%, -50%);
    background: transparent;
    border: 4px solid #00e8e4;
    border-radius: 50%;
  }

  .SynopsisCard {
    position: relative;
    height: 80%;
    background: transparent;
  }

  .dateRelease {
    position: absolute;
    left: 100px;
    font-size: 19px;
    color: #999;
  }

  .synopsisMovie {
    position: relative;
    padding: 50px 30px 15px 30px;
    margin-bottom: 10px;
    height: 130px;
    font-family: 'Lato';
    font-size: 17px;
    text-align: justify;
    /* background: rgb(17,97,147); */
    overflow: hidden;
  }

  .synopsisMovie:after {
    position: absolute;
    content: '';
    bottom: 0;
    left: 0;
    width: 100%;
    height: 50px;
    background: linear-gradient(transparent, #ebebeb);
  }

  .categoriesMovie {
    display: flex;
    padding-left: 30px;
    
  }
  .categoriesMovie li {
    list-style: none;
    background: red;
    padding: 3px 6px;
    margin-right: 10px;
    border: 1px solid #116193;
    border-radius: 25px;
    background: #fff;
    font-size: 14px;
    color: #116193;
  }
</style>