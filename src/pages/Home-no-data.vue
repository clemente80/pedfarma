<template>
  <div class='ContentSearch'>
      <input class='InputSearch' placeholder='Busque um filme por nome, ano ou gênero...' onChange={handleSearch}/>
      <section class='CardSearched'>
          <div class='PoserCard'>
              <div class='backgroundCard' :style="{'background-image': 'url(' + require('../assets/poser01.jpg') + ')'}"></div>
              <!-- <div style={{backgroundImage: `url(https://image.tmdb.org/t/p/w500/${myMovie.poster_path})`}}></div> -->
          </div>
          <div class='DescriptionCard'>
              <div class='TitleCard'><span>Os Vingadores - The Avengers</span><span>77%</span></div>
              <!-- <TitleCard><span>{myMovie.title}</span><span>{Math.round(myMovie.vote_average/0.1)}%</span></TitleCard> -->
              <div class='SynopsisCard'>
                  <div class='dateRelease'>25-04-2012</div>
                  <!-- <Moment format="DD/MM/YYYY">{myMovie.release_date}</Moment> -->
                  <!-- <div className='dateRelease'>{format(new Date(myMovie.release_date), 'dd/MM/yyyy')}</div> -->
                  <!-- <div className='dateRelease'>{myMovie.release_date}</div> -->
                  <div class='synopsisMovie'>Loki, o irmão de Thor, ganha acesso ao poder ilimitado do cubo cósmico ao roubá-lo de dentro das instalações da S.H.I.E.L.D. Nick Fury, o diretor desta agência internacional que mantém a paz, logo reúne os únicos super-heróis que serão capazes de defender a Terra de ameaças sem precedentes. Homem de Ferro, Capitão América, Hulk, Thor, Viúva Negra e Gavião Arqueiro formam o time dos sonhos de Fury, mas eles precisam aprender a colocar os egos de lado e agir como um grupo em prol da humanidade.
                  </div>
                  <!-- <div className='synopsisMovie'>{myMovie.overview}
                  </div> -->
                  <div className='categoriesMovie'>
                          <li>Ação</li>
                          <li>Aventura</li>
                          <li>Ficção Cientifica</li>
                      <!-- {myMovie.genre_ids.map((categ, key) => (
                          <li key={key}>{searchGenres(categ)}</li>
                      ))} -->
                  </div>
              </div>
          </div>
      </section>
      <section class='CardSearched'>
          <div class='PoserCard'>
              <div class='backgroundCard' :style="{'background-image': 'url(' + require('../assets/poser02.jpg') + ')'}"></div>
              <!-- <div style={{backgroundImage: `url(https://image.tmdb.org/t/p/w500/${myMovie.poster_path})`}}></div> -->
          </div>
          <div class='DescriptionCard'>
              <div class='TitleCard'><span>Alladin</span><span>71%</span></div>
              <!-- <TitleCard><span>{myMovie.title}</span><span>{Math.round(myMovie.vote_average/0.1)}%</span></TitleCard> -->
              <div class='SynopsisCard'>
                  <div class='dateRelease'>22-05-2019</div>
                  <!-- <Moment format="DD/MM/YYYY">{myMovie.release_date}</Moment> -->
                  <!-- <div className='dateRelease'>{format(new Date(myMovie.release_date), 'dd/MM/yyyy')}</div> -->
                  <!-- <div className='dateRelease'>{myMovie.release_date}</div> -->
                  <div class='synopsisMovie'>Um jovem humilde descobre uma lâmpada mágica, com um gênio que pode lhe conceder desejos. Agora o rapaz quer conquistar a moça por quem se apaixonou, mas o que ele não sabe é que a jovem é uma princesa que está prestes a se noivar. Com a ajuda do Gênio, ele tenta se passar por um príncipe para conquistar o amor da moça e a confiança do pai dela.
                  </div>
                  <!-- <div className='synopsisMovie'>{myMovie.overview}
                  </div> -->
                  <div className='categoriesMovie'>
                          <li>Aventura</li>
                          <li>Família</li>
                          <li>Fantasia</li>
                          <li>Romance</li>
                      <!-- {myMovie.genre_ids.map((categ, key) => (
                          <li key={key}>{searchGenres(categ)}</li>
                      ))} -->
                  </div>
              </div>
          </div>
      </section>
      <section class='CardSearched'>
          <div class='PoserCard'>
              <div class='backgroundCard' :style="{'background-image': 'url(' + require('../assets/poser03.jpg') + ')'}"></div>
              <!-- <div style={{backgroundImage: `url(https://image.tmdb.org/t/p/w500/${myMovie.poster_path})`}}></div> -->
          </div>
          <div class='DescriptionCard'>
              <div class='TitleCard'><span>Guerra nas Estrelas: O Império Contra-Ataca</span><span>84%</span></div>
              <!-- <TitleCard><span>{myMovie.title}</span><span>{Math.round(myMovie.vote_average/0.1)}%</span></TitleCard> -->
              <div class='SynopsisCard'>
                  <div class='dateRelease'>20/05/1980</div>
                  <!-- <Moment format="DD/MM/YYYY">{myMovie.release_date}</Moment> -->
                  <!-- <div className='dateRelease'>{format(new Date(myMovie.release_date), 'dd/MM/yyyy')}</div> -->
                  <!-- <div className='dateRelease'>{myMovie.release_date}</div> -->
                  <div class='synopsisMovie'>As forças imperais comandadas por Darth Vader (David Prowse) lançam um ataque contra os membros da resistência, que são obrigados a fugir. Enquanto isso Luke Skywalker (Mark Hamill) tenta encontrar o Mestre Yoda, que poderá ensiná-lo a dominar a "Força" e torná-lo um cavaleiro jedi. No entanto, Darth Vader planeja levá-lo para o lado negro da "Força".
                  </div>
                  <!-- <div className='synopsisMovie'>{myMovie.overview}
                  </div> -->
                  <div className='categoriesMovie'>
                          <li>Ação</li>
                          <li>Aventura</li>
                          <li>Ficção Cientifica</li>
                      <!-- {myMovie.genre_ids.map((categ, key) => (
                          <li key={key}>{searchGenres(categ)}</li>
                      ))} -->
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
// import styled from 'vue-styled-components';

// export const ContentSearch = styled.section`
//   background: #ccc;
//   border: 1px solid #fff;
// `;

export default {
  name: 'CardMovie',
  props: {
    msg: String
  },
  // components: {
  //   ContentSearch
  // },
}
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