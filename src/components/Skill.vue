<template>
    <section id="cards">
        <div class="container">
            <div class="row">
                <div class="col-12">
                   <h1>Сдаелаем Ваш проект уникальным и качественным </h1> 
                </div>
                <div class="col-lg-3 col-md-6" v-for="(n, i) in card" :key="n._id" :name="i">
                    <div class="card text-center mb-4">
                        <div class="card-top">
                            <h3>{{ n.heading }}</h3>
                        </div>
                        <div class="card-img">
                            <img :src="n.img" alt="">
                        </div>
                        <div class="card-body">
                            <p>{{ n.title }}</p>
                            <a href="#!" class="btn btn-outline-primary">Заказать</a>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>
</template>

<script>
// import $ from 'jquery'
import { gsap } from 'gsap';
import { CSSPlugin } from 'gsap/CSSPlugin'
gsap.registerPlugin(CSSPlugin);
 
const card = [
  {
    _id:'1',
    img: require('../assets/cardSvg/card2.svg'),
    heading:'Веб-сайты',
    title: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit ut aliquam, purus sit amet luctus venenatis ',
    price: 'от 1000 $'
  },
  {
    _id:'2',
    img: require('../assets/cardSvg/card3.svg'),
    heading:'Приложения',
    title: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit ut aliquam, purus sit amet luctus venenatis ',
    price: 'от 1000 $'
  },
  {
    _id:'3',
    img: require('../assets/cardSvg/card1.svg'),
    heading:'Телеграм боты',
    title: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit ut aliquam, purus sit amet luctus venenatis ',
    price: 'от 1000 $'
  },
  {
    _id:'4',
    img: require('../assets/cardSvg/card4.svg'),
    heading:'SEO оптимизация',
    title: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit ut aliquam, purus sit amet luctus venenatis ',
    price: 'от 1000 $'
  },
] 

export default {
  name: 'Skill',
  data(){
      return{
        card: card,
      }
  },
  mounted () {
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
section{
    width: 100%;
    background: linear-gradient(180deg, rgba(224, 223, 255, 0.8) 0%, rgba(236, 236, 255,
     0.5) 100%);
     padding: 100px 0;
}
section h1{
    font-size: 36px;
    font-weight: 700;
    margin-bottom: 40px;
    text-align: center;
}
.card{
    border-radius: 10px;
    padding: 15px 10px;
    transition: 0.5s;
}
.card:hover{
    transform: scale(1.05);
    transition: 0.5s;

}
.card .btn {
    border-radius: 10em !important;
    padding: 10px 30px;
    box-shadow: 0 5px 11px 0 rgba(0,0,0,0.18), 0 4px 15px 0 rgba(0,0,0,0.15);
}
.card .btn:focus {
    box-shadow: 0 5px 11px 0 rgba(0,0,0,0.18), 0 4px 15px 0 rgba(0,0,0,0.15) !important;
}
.card h3{
    font-size: 24px;
    margin-bottom: 25px;
    font-weight: 600;
}
.card img{
    margin-bottom: 25px;
}
.card p{
    margin-bottom:25px;
}
</style>
