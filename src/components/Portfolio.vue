<template>
    <section class="portfolio" id="portfolio">
        <div class="container-fluid">
            <div class="row">
              <div class="col-12">
                <h1>
                  Bizning ishimiz:
                </h1>
              </div>
            </div>
            <swiper class="swiper" :options="swiperOption">
                <swiper-slide v-for="(n, i) in card" :key="n._id">
                  <a :href="n.link" class="wrapper">
                    <img :src="n.img" :alt="i">
                  </a>
                </swiper-slide>
                <div class="swiper-pagination" slot="pagination"></div>
            </swiper>
        </div>
    </section>
</template>

<script>
  import swiperCore, {Pagination} from 'swiper'
  import { Swiper, SwiperSlide } from 'vue-awesome-swiper'
  import '../assets/css/swiper.css'
  import { mapGetters } from 'vuex'
  swiperCore.use([Pagination])
  export default {
    name: 'Portfolio',
    components: {
      Swiper,
      SwiperSlide
    },
    computed: mapGetters(['card']),
    mounted () {
      this.$store.dispatch('fetchCard')
    },
    data() {
      return {
        swiperOption: {
          slidesPerView: 3,
          slidesPerColumn: 3,
          pagination: {
            el: '.swiper-pagination',
            clickable: true
          },
          breakpoints: {
            1024: {
              slidesPerView: 3,
              slidesPerColumn: 2,
            },
            768: {
              slidesPerView: 2,
              slidesPerColumn: 2,
              centeredSlides: true,
            },
            640: {
              slidesPerView: 2,
              slidesPerColumn: 2,
              centeredSlides: true,
            },
            320: {
              slidesPerView: 1,
              slidesPerColumn: 2,
              centeredSlides: true,
            }
          }
        }
      }
    }
  }
</script>

<style>
section.portfolio{
    padding: 100px 0;
}
section h1{
    font-size: 36px;
    font-weight: 700;
    margin-bottom: 40px;
    text-align: center;
}
  .swiper {
    height: 600px;
    margin-left: auto;
    margin-right: auto;
  }
  .swiper-slide {
      height: 270px;
      background: #eee;
      border: 1px solid rgb(119, 34, 34);
   }
   .swiper-slide .wrapper img{
     width: 100%;
     height: 100%;
     object-fit: cover;
     transition: .3s ease-in-out;
   }
   .swiper-slide .wrapper{
     display: block;
     width: 100%;
     height: 100%;
     overflow: hidden;
   }
   .swiper-slide .wrapper:hover img{
     transform: scale(1.3) rotate(15deg);
   }
   .swiper-pagination{
       align-items: center;
   }
   .swiper-pagination .swiper-pagination-bullet.swiper-pagination-bullet-active{
       transition: 0.3s;
       width: 20px !important;
       height: 20px !important;
       background: #2824EA;
   }
   .swiper-pagination .swiper-pagination-bullet{
       width: 100px !important;
       opacity: 1;
       height: 20px !important;
       border-radius: 10em !important;
       transition: 0.3s;
       border: 2px solid #2824EA;
       background: #eee;
   }
   @media (max-width:500px){
      .swiper-pagination .swiper-pagination-bullet{
        width: 20px !important;
        height: 20px !important;
      }
   }
</style>