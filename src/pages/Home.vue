<template>
   <main v-if="sections">
      <!-- <img alt="Vue logo" src="../assets/logo.png" /> -->

      <Intro v-bind:section="sections.intro"  /> 
      <About v-bind:section="sections.about"  /> 
      <Specs v-bind:section="sections.specs"  /> 
   </main>
</template>

<script>
// @ is an alias to /src
import Intro from "@/components/home/Intro.vue";
import About from "@/components/home/About.vue";
import Specs from "@/components/home/Specs.vue";

export default {
   name: "Home",
   data() {
      return {
         title: "Home page",
         sections: null, 
      };
   },
   components: {
      Intro,About, Specs
   },

   created() {
      fetch("data/home-page.json")
         .then((result) => result.json())
         .then((data) => {
            console.log(data);

            this.sections = data;
         });
   },
};
</script>
