<template>
    <section id="cards">
        <div class="container">
            <div class="row">
                <div class="col-12">
                   <h1>Sizning loyihangizni noyob va yuqori sifatda bajarib beramiz!
                       <h3 class="mt-4">Xizmatlarimiz:</h3> 
                        </h1> 
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
                            <a href="#!" v-ripple class="btn btn-outline-primary">Buyurtma berish</a>
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
    heading:'Veb saytlar',
    title: "Veb sayt yaratuvchi - faoliyatingiz haqida foydalanuvchilarga zarur barcha ma'lumotlarning elektron bazasi sifatida platforma yaratish bilan shug'ullanadi",
    price: 'от 1000 $'
  },
  {
    _id:'2',
    img: require('../assets/cardSvg/card3.svg'),
    heading:'Android',
    title: "Android ustasi - turli aloqa vositalari: planshet, smartfonlar, soatlar va raqamli media playerlarida ishlatiladigan turli Android operatsion tizimlarini yaratish uning vazifasi",
    price: 'от 1000 $'
  },
  {
    _id:'3',
    img: require('../assets/cardSvg/card1.svg'),
    heading:'Telegram botlar',
    title: "Telegram bot yaratuvchi -  O'zbekiston miqyosida onlayn biznes faoliyatida eng ko'p foydalaniladigan messenjer - Telegramdagi xabar almashinuv ishlaringizni avtomatlashtirib berish uning vazifasi",
    price: 'от 1000 $'
  },
  {
    _id:'4',
    img: require('../assets/cardSvg/card4.svg'),
    heading:'SEO optimizatsiya',
    title: "SEO optimizatsiyasi ustasi - qidiruv tizimlarida saytingizni yuqori o'rinni egallashini ta'minlashga erishishda yordamchi",
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
}
.card .btn:focus {
    box-shadow:none !important;
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

