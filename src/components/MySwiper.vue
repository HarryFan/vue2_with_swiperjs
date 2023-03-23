<template>
  <div class="swiper-container">
    <swiper
      class="swiper-wrapper"
      :options="swiperOption"
      @slideChange="onSlideChange"
      ref="mySwiper"
    >
    <swiper-slide>
        <img src="https://picsum.photos/id/100/900/600" alt="Image 1" />
      </swiper-slide>
      <swiper-slide>
        <img src="https://picsum.photos/id/101/900/600" alt="Image 2" />
      </swiper-slide>
      <swiper-slide>
        <img src="https://picsum.photos/id/102/900/600" alt="Image 3" />
      </swiper-slide>

      <!-- Add more slides if needed -->

      <!-- Swiper pagination -->
      <div class="swiper-pagination" slot="pagination"></div>

      <!-- Swiper navigation -->
      <div class="swiper-button-prev" slot="button-prev"></div>
      <div class="swiper-button-next" slot="button-next"></div>
    </swiper>
  </div>
</template>
這將使每個輪播圖像使用不同的 Picsum 圖像





<script>
// import Swiper JS
import VueAwesomeSwiper from 'vue-awesome-swiper';
import 'swiper/css/swiper.min.css';


export default {
  name: 'MySwiper',
  components: {
    swiper: VueAwesomeSwiper.swiper,
    swiperSlide: VueAwesomeSwiper.swiperSlide
  },
  data() {
    return {
      swiperOption: {
        loop: true,
        pagination: {
          el: '.swiper-pagination',
        },
        navigation: {
          nextEl: '.swiper-button-next',
          prevEl: '.swiper-button-prev',
        },
      },
    };
  },
  methods: {
    onSlideChange() {
      console.log('Current slide:', this.$refs.mySwiper.swiper.realIndex);
    },
  },
};
</script>

<style>
  .swiper-container {
    width: 100%;
    height: 100%;
  }

  .swiper-slide {
    text-align: center;
    font-size: 18px;
    background: #fff;
  }
</style>
