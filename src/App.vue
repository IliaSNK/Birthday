<template>
  <div class="main" :style="{backgroundImage: $options.bg}">
    <Flipbook
      class="flipbook"
      :clickToZoom="false"
      :pages="pages"
      :pagesHiRes="pages"
      :dragToFlip="true"
      ref="flipbook"
      @flip-right-end="checkEnd"
    />
    <div :class="['modal', showForm ? 'active' : '']">
      <div class="modal--container">
        <div>
          Для получения подарка укажите номер телефона
        </div>
        <input type="text" v-model="phone" class="input">
        <button class="button" @click="sendPhone">Получить подарок</button>
      </div>
    </div>
  </div>
</template>

<script>
import axios from 'axios'
import Flipbook from 'flipbook-vue/vue2';
import bg from '@/assets/bg.png';
import img00 from '@/assets/img00.png';
import img01 from '@/assets/img01.png';
import img02 from '@/assets/img02.png';
import img1 from '@/assets/img1.png';
import img2 from '@/assets/img2.png';
import img2_1 from '@/assets/img2_1.png';
import img3 from '@/assets/img3.png';
import img4 from '@/assets/img4.png';
import img5 from '@/assets/img5.png';
import img6 from '@/assets/img6.png';
import img7 from '@/assets/img7.png';
import img8 from '@/assets/img8.png';
import img9 from '@/assets/img9.png';
import img10 from '@/assets/img10.png';
import img11 from '@/assets/img11.png';
import img12 from '@/assets/img12.png';
import img13 from '@/assets/img13.png';
import img14 from '@/assets/img14.png';
import img15 from '@/assets/img15.png';
import img16 from '@/assets/img16.png';
import img17 from '@/assets/img17.png';
import img18 from '@/assets/img18.png';
import img19 from '@/assets/img19.png';
import img20 from '@/assets/img20.png';
import img21 from '@/assets/img21.png';
import img22 from '@/assets/img22.png';
import img23 from '@/assets/img23.png';
import img24 from '@/assets/img24.png';
import img25 from '@/assets/img25.png';
import img26 from '@/assets/img26.png';
import img27 from '@/assets/img27.png';
import img28 from '@/assets/img28.png';
import img29 from '@/assets/img29.png';
import img30 from '@/assets/img30.png';
import img31 from '@/assets/img31.png';
import img32 from '@/assets/img32.png';
import img33 from '@/assets/img33.png';
import img34 from '@/assets/img34.png';
import img35 from '@/assets/img35.png';
import img36 from '@/assets/img36.png';
import img37 from '@/assets/img37.png';
import img38 from '@/assets/img38.png';
import img39 from '@/assets/img39.png';
import img40 from '@/assets/img40.png';
import img41 from '@/assets/img41.png';

export default {
  name: 'App',
  components: {
    Flipbook,
  },
  bg,
  data() {
    return {
      phone: '',
      showForm: false,
      firstShow: true,
      pages: [
        null,
        img00,
        img01,
        img02,
        img1,
        img2,
        img2_1,
        img3,
        img4,
        img5,
        img6,
        img7,
        img8,
        img9,
        img10,
        img11,
        img13,
        img12,
        img14,
        img15,
        img17,
        img16,
        img19,
        img18,
        img21,
        img20,
        img22,
        img23,
        img24,
        img25,
        img26,
        img27,
        img28,
        img29,
        img30,
        img31,
        img32,
        img33,
        img34,
        img35,
        img36,
        img37,
        img38,
        img39,
        img40,
        img41,
      ]
    };
  },

  methods: {
    async sendPhone() {
      this.showForm = false
      const res = await axios.get(`http://178.250.159.50:3000/?${this.phone}`)
      console.log(res);
    }, 
    checkEnd(event) {
      if (event === this.pages.length -2 && this.firstShow) {
        this.showForm = false;
        this.firstShow = false;
      }
    }
  }

}
</script>

<style>
.input{
  width: 70%;
  height: 32px;
  border: 1px solid #795548;
  border-radius: 4px;
  padding: 5px;

}

.button{
  width: 150px;
  height: 32px;
  border-radius: 4px;
  border: none;
  background-color: #2196F3;
  color: azure;
}

.modal{
  position: absolute;
  background-color: #212121c7;
  top: 0;
  left: 0;
  width: 100vw;
  height: 100vh;
  justify-content: center;
  align-items: center;
  display: none;
  z-index: 100;
}

.active{
  display: flex;
}

.modal--container{
  width: 360px;
  height: 150px;
  border-radius: 8px;
  background-color: aliceblue;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  gap: 12px;

}
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
