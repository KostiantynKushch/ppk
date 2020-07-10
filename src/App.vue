<template>
  <div class="off-canvas-wrapper">
    <div class="off-canvas position-left" :class="{'is-open' : isMenuOpen}" id="offCanvas" data-off-canvas>
       <MobNav/>
    </div>
    <div class="off-canvas-content" data-off-canvas-content>
      <v-header />

      <router-view />

      <Footer />
    </div>
  </div>
</template>

<script>
import {eventBus} from '@/main.js';

import Header from "@/components/Header.vue";
import Footer from "@/components/Footer.vue";
import MobNav from "@/components/MobNav.vue";

export default {
   data(){
      return{
         isMenuOpen: false
      }
   },
  components: {
    "v-header": Header,
    Footer,
    MobNav
  },
  created(){
     eventBus.$on('toggleMenu', () => {
        this.isMenuOpen = !this.isMenuOpen
     });
  }
};
</script>

<style lang="scss">
@import "@/assets/scss/main";
</style>
