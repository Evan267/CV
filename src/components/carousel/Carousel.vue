<template>
  <div>
    <div class="carousel__pagination">
       <button v-for="n in slidesCount" :key="n" @click="goto(n-1)" :class="{active: n-1 == index}">Projet {{n}}</button>
     </div>
    <div class="carousel">
     <slot></slot>
     <button class="carousel__nav carousel__next" @click.prevent="next"><i class="fas fa-chevron-right"></i></button>
     <button class="carousel__nav carousel__prev" @click.prevent="prev"><i class="fas fa-chevron-left"></i></button>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Carousel',
  data() {
    return {
      index: 0,
      slides: [],
      direction: null
    };
  },
  mounted () {
    this.slides = this.$children
    this.slides.forEach((slide, i) => {
      slide.index = i
    })
  },
  computed: {
    slidesCount (){
      return this.slides.length
    }
  },
  methods: {
    next(){
      this.index++;
      this.direction = "right";
      if(this.index >= this.slidesCount){
        this.index = 0;
      }
    },
    prev(){
      this.index--;
      this.direction = "left";
      if(this.index < 0){
        this.index = this.slidesCount - 1
      }
    },
    goto(index){
      this.direction = index > this.index ? 'right' : 'left'
      this.index=index;
    }
  }
}
</script>


<style lang="scss">
.carousel{
  position: relative;
  overflow: hidden;
  height: 50vw;
  &__nav{
    position: absolute;
    top: 50%;
    left: 10px;
    width: 63px;
    height: 63px;
    background-color: transparent;
    border:none;
    &:hover{
      opacity: 50%;
    }
  }
  &__next{
    right: 10px;
    left: auto;
  }
  &__pagination{
    width: 100%;
    display: flex;
    justify-content: space-around;
    button{
      background-color: transparent;
      border: none;
    }
    button.active{
      background-color: blue;
    }
  }
}
</style>