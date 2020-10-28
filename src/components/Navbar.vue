<template>
  <nav id="nav" class="navbar fixed-top">
    <div class="container">
      <a class="navbar-brand" href="#"><img width="100px" :src="require('../assets/nine.png')" alt=""></a>
      <!-- <button data-target="#collapseNav"></button> -->
      <div class="navbar-collapse" id="collapseNav">
        <ul class="navbar-nav" style="margin:0;">
          <li class="nav-item">
            <a href="#home" class="nav-link active">Home</a>
          </li>
          <li class="nav-item">
            <a href="#cards" class="nav-link">About</a>
          </li>
          <li class="nav-item">
            <a href="#skill" class="nav-link">Skills</a>
          </li>
          <li class="nav-item">
            <a href="#portfolio" class="nav-link">Portfolio</a>
          </li>
          <li class="nav-item">
            <a href="#contact" class="nav-link">Contact Us</a>
          </li>
        </ul>
      </div>
    </div>
  </nav>
</template>

<script>
import $ from 'jquery'
import { gsap } from 'gsap';
import { CSSPlugin } from 'gsap/CSSPlugin'
gsap.registerPlugin(CSSPlugin);
export default {
  name: 'Navbar',
  mounted () {
    $(window).scroll(function () {
      let $scroll = $(this).scrollTop();
        console.log($scroll);
        if ($scroll >= 100) {
            $('#nav').addClass('active');
        }
        else {
            $('#nav').removeClass('active');
        }
       let $links = $('.navbar .navbar-nav .nav-item .nav-link')
       console.log($links);
        $links.each(function () {
            let $id = $(this).attr('href');
            console.log($id);
            let $target = $($id).offset().top-100;
            if ($scroll >= $target) {
                $links.removeClass('active')
                $(this).addClass('active')
            }
        })  
    });
    let links = ('#nav .nav-link');
    $(links).on('click', function (e) {
        e.preventDefault();
        $(links).removeClass('active');
        $(this).addClass('active');
        let id = $(this).attr('href');
        let target = $(id).offset().top;
        $('html, body').animate({
            scrollTop: target,
        }, 1000);
    });
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.fixed-top{
  position: fixed !important;
  top: 0;
  left: 0;
  right: 0;
  width: 100%;
  height: auto;
  transition: 1s;
}
.fixed-top.active{
  background: rgba(255, 255, 255, 0.9);
  transition: 1s;
}
</style>
