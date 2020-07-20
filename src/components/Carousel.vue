<!-- 
NOTES

For mobile devices: use 'scroll-snap-type: (x | y) mandatory' in container and 'scroll-snap-stop: always' in child
For desktop: ... not tested yet

Scroll-snap-stop is not supported on Safari, so try using '-webkit-overflow-scrolling: auto' for Safari devices
  ('scrolling-auto' from tailwind might just do it)

 -->

<template>
  <div class="flex flex-no-wrap overflow-x-auto mx-8 scrolling-auto">
    <Tile v-for="num in numOfTiles" :key="num" />
  </div>
</template>

<script>
import Tile from '@/components/Tile.vue'

export default {
  components: {
    Tile
  },
  props: {
    msg: String
  },
  data: function () {
    return {
      numOfTiles: [1, 2, 3, 4, 5, 6, 7, 8],
    }
  },
}
</script>

<style scoped>
  div {
    scroll-snap-type: x mandatory;
  }
</style>
