<template>
  <div class="main" :style="{backgroundImage: $options.bg}">
    <button @click="flipTo=4">Test</button>
    <Flipbook
      class="flipbook"
      :clickToZoom="false"
      :pages="pages"
      :pagesHiRes="pages"
      :dragToFlip="true"
      @flip-left-end="test"
      @flip-right-end="test"
      ref="flipbook"
    />
  </div>
</template>

<script>
import Flipbook from 'flipbook-vue/vue2';
import bg from '@/assets/bg.png';
import img1 from '@/assets/img1.png';
import img2 from '@/assets/img2.png';
import img3 from '@/assets/img3.png';
// import img4 from '@/assets/img4.png';
export default {
  name: 'App',
  components: {
    Flipbook,
  },
  bg,
  data() {
    return {
      flipTo: null,
      currentPage: 1,
      pages: [
        null,
        img1,
        img2,
        img3,
        img1,
        img2,
        img3,
        img1,
        img2,
        img3,
        img1,
        img2,
        img3,
        // img1,
        // img2,
        // img3,
        // img1,
        // img2,
        // img3,
        // img1,
        // img2,
        // img3,
        // img1,
        // img2,
        // img3,
        // img1,
        // img2,
        // img3,
        // img1,
        // img2,
        // img3,
      ]
    };
  },

}
</script>

<style>
*{
  padding: 0;
  margin: 0;
}
.page{
  width: 300px;
  height: 600px;
}
.flipbook {
  width: 100vw;
  height: 100vh;
  background-image: url(@/assets/bg.png);
}
</style>
