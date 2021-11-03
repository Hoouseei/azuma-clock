<template>
  <div class="pie-wrapper">
    <p class="pie" :style="{backgroundImage: `conic-gradient(${color} 0% ${position*100}%, #fff ${position*100}% 100%)`}">
    </p>
    <p class="time"><span><em>{{time}}</em><small> {{unit}}</small></span></p>
  </div>
</template>

<script>
export default {
  props: [ 'time', 'unit' , 'position', 'color']
}
</script>

<style lang="stylus" scoped>
.pie
  width 50px
  height 50px
  margin-right 24px
  border-radius: 50%
  &-wrapper
    display flex
    align-items: center

.time
  font-family: 'Noto Sans CJK JP'
  font-weight 600
  em
    font-size 28px
    font-style normal
    font-weight 800
    letter-spacing -1px
  // small
</style>
