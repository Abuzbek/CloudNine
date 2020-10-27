<template>
  <nav class="navbar fixed-top">
    <div class="container">
      <a class="navbar-brand" href="#"><img width="100px" :src="require('../assets/nine.png')" alt=""></a>
      <!-- <button data-target="#collapseNav"></button> -->
      <div class="navbar-collapse" id="collapseNav">
        <ul class="navbar-nav" style="margin:0;">
          <li class="nav-item">
            <a href="#home" class="nav-link active">Home</a>
          </li>
          <li class="nav-item">
            <a href="#about" class="nav-link">About</a>
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
import { gsap } from 'gsap';
import { CSSPlugin } from 'gsap/CSSPlugin'
gsap.registerPlugin(CSSPlugin);
export default {
  name: 'Navbar',
  mounted () {

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
}
.fixed-top.active{
  background: #ffffff;
}
</style>
