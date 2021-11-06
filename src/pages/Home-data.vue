<template>
  <div id='content-search' class='ContentSearch'>
      <input class='InputSearch' placeholder='Busque um filme por nome, ano ou gênero...' />
      <section class='CardSearched' v-for='(item, index) in items' :key='index'>
          <div class='PoserCard'>
              <div class='backgroundCard' :style="{'background-image': 'url(' + require('../assets/'+item.file) + ')'}"></div>
          </div>
          <div class='DescriptionCard'>
              <div class='TitleCard'><span>{{item.name}}</span><span>{{item.percentage}}%</span></div>
              <div class='SynopsisCard'>
                  <div class='dateRelease'>{{item.date}}</div>
                  <div class='synopsisMovie'>{{item.synopsis}}
                  </div>
                  <div className='categoriesMovie'>
                          <li v-for='(categ, index) in item.categ' :key='index'>{{categ}}</li>
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

export default{
  el: '#content-search',
  data() {
    return {
      items: [
        {
          file: 'poser01.jpg',
          name: 'Os Vingadores - The Avengers',
          percentage: '77',
          date: '25-04-2012',
          synopsis: 'Loki, o irmão de Thor, ganha acesso ao poder ilimitado do cubo cósmico ao roubá-lo de dentro das instalações da S.H.I.E.L.D. Nick Fury, o diretor desta agência internacional que mantém a paz, logo reúne os únicos super-heróis que serão capazes de defender a Terra de ameaças sem precedentes. Homem de Ferro, Capitão América, Hulk, Thor, Viúva Negra e Gavião Arqueiro formam o time dos sonhos de Fury, mas eles precisam aprender a colocar os egos de lado e agir como um grupo em prol da humanidade.',
          categ: [
            'Ação', 'Aventura', 'Ficção Científica'
          ]
        },{
          file: 'poser02.jpg',
          name: 'Alladin',
          percentage: '71',
          date: '22-05-2019',
          synopsis: 'Um jovem humilde descobre uma lâmpada mágica, com um gênio que pode lhe conceder desejos. Agora o rapaz quer conquistar a moça por quem se apaixonou, mas o que ele não sabe é que a jovem é uma princesa que está prestes a se noivar. Com a ajuda do Gênio, ele tenta se passar por um príncipe para conquistar o amor da moça e a confiança do pai dela.',
          categ: [
            'Ação', 'Aventura', 'Fantasia', 'Ficção Científica'
          ]
        },{
          file: 'poser03.jpg',
          name: 'Guerra nas Estrelas: O Império Contra-Ataca',
          percentage: '84',
          date: '20/05/1980',
          synopsis: 'As forças imperais comandadas por Darth Vader (David Prowse) lançam um ataque contra os membros da resistência, que são obrigados a fugir. Enquanto isso Luke Skywalker (Mark Hamill) tenta encontrar o Mestre Yoda, que poderá ensiná-lo a dominar a "Força" e torná-lo um cavaleiro jedi. No entanto, Darth Vader planeja levá-lo para o lado negro da "Força".',
          categ: [
            'Ação', 'Aventura', 'Ficção Científica'
          ]
        },
      ]
    }
  }
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