<template>
    <transition :name="transition">
      <div v-show="visible">
        <slot></slot>
      </div>
    </transition>
</template>

<script>
export default {
  name: 'CarouselSlide',
  data() {
      return {
          index: 0,
      };
  },
  computed: {
    transition(){
      if(this.$parent.direction){
        return "slide-" + this.$parent.direction
      }else{
        return null
      }
    },
    visible(){
      return this.index === this.$parent.index
    }
  }
}
</script>

