<template>
  <section class="ba-section">
    <div class="row column ba-container">
      <h2 class="ba-section-title ba-section-title--about">{{ section.title }}</h2>

      <div class="row">
        <div class="column small-12 medium-8 medium-offset-2 large-6 large-offset-3">
          <div class="ba-about-desc">
            <p>{{section.content}}</p>

           <div class="ba-about-desc__img">
               <img :src="section.img" :alt="section.title" />
           </div>
           <!-- /.ba-about-desc__img -->
          </div>
          <!-- /.ba-about-desc -->
        </div>
        <!-- /.column small-12 -->
      </div>
      <!-- /.row -->
    </div>
    <!-- /.ba-container -->
  </section>
</template>

<script>
export default {
  props: ["section"]
};
</script>

<style lang="scss">
.ba-about-desc{

   &__img{
      @include breakpoint(small down){
         margin-left: -33px;
         margin-right: -33px;
      }
   }

   @include breakpoint(medium) {
    padding-top: 90px;
    position: relative;

    &:after{
       content: '';
       width: 115px;
       height: 237px;
       position: absolute;
       top: 0;
       left: 100%;
       margin-left: -20px;
       border:  7px solid $primary-color;
       border-width: 7px 7px 0 0;
    }
    &__img{
       position: relative;
       padding-top: 66px;
          &:after{
             content: '';
             width: 96px;
             height: 191px;
             position: absolute;
             background: $primary-color;
            bottom: 13%;
            right: 100%;
          }
    }
  }
   
}
.ba-section {
  padding: 44px 0;

  @include breakpoint(medium) {
    padding: 90px 0 78px;
  }
}

.ba-section-title {
   margin-bottom: 29px;
  &:after {
    content: "";
    display: block;
    height: 7px;
    width: 253px;
    background: $primary-color;
    margin-top: 10px;
  }
  &--about{
      @include breakpoint(medium) {
    margin-bottom: 0;
  }
  }
}
</style>
