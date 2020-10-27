<template>
    <section>
        <div class="container">
            <div class="row">
                <div class="col-lg-3 col-md-6">
                    <div class="card">
                        <div class="card-top">
                            <h3></h3>
                        </div>
                        <div class="card-img">

                        </div>
                        <div class="card-body">

                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>
</template>

<script>
import { gsap } from 'gsap';
import { CSSPlugin } from 'gsap/CSSPlugin'
gsap.registerPlugin(CSSPlugin);
export default {
  name: 'Skill',
  mounted () {
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
section{
    width: 100%;
    height: 100vh;
    background: linear-gradient(180deg, rgba(224, 223, 255, 0.8) 0%, rgba(236, 236, 255,
     0.5) 100%);
}
</style>
