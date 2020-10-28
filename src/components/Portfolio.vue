<template>
    <section class="portfolio">
        <div class="container-fluid">
            <swiper class="swiper" :options="swiperOption">
                <swiper-slide></swiper-slide>
                <swiper-slide></swiper-slide>
                <swiper-slide></swiper-slide>
                <swiper-slide></swiper-slide>
                <swiper-slide></swiper-slide>
                <swiper-slide></swiper-slide>
                <swiper-slide></swiper-slide>
                <swiper-slide></swiper-slide>
                <swiper-slide></swiper-slide>
                <swiper-slide></swiper-slide>
                <div class="swiper-pagination" slot="pagination"></div>
            </swiper>
        </div>
    </section>
</template>

<script>
  import swiperCore, {Pagination} from 'swiper'
  import { Swiper, SwiperSlide } from 'vue-awesome-swiper'
  import '../assets/css/swiper.css'
  swiperCore.use([Pagination])
  export default {
    name: 'Portfolio',
    components: {
      Swiper,
      SwiperSlide
    },
    data() {
      return {
        swiperOption: {
          slidesPerView: 3,
          slidesPerColumn: 2,
          pagination: {
            el: '.swiper-pagination',
            clickable: true
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
</style>