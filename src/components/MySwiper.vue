<template>
  <div class="swiper-container">
    <p>
      這段程式碼將會在網頁上顯示一個輪播圖，其中可以透過分頁器或是導航器切換圖片。
    </p>
    <p>
      在這個範例中，有三張圖片，並且設定了循環播放（loop: true）。當 Slide 改變時，會觸發 onSlideChange 事件，並在 Console 中顯示當前的 Slide 編號。
    </p>
    <!-- 容器 -->
    <swiper class="swiper-wrapper" :options="swiperOption" @slideChange="onSlideChange" ref="mySwiper">
      <!-- 輪播的各個 Slide -->
      <swiper-slide>
        <img src="https://picsum.photos/id/100/900/600" alt="圖片 1" />
      </swiper-slide>
      <swiper-slide>
        <img src="https://picsum.photos/id/101/900/600" alt="圖片 2" />
      </swiper-slide>
      <swiper-slide>
        <img src="https://picsum.photos/id/102/900/600" alt="圖片 3" />
      </swiper-slide>
      <!-- 如果需要，可以再加入更多的 Slide -->

      <!-- 輪播的分頁器 -->
      <div class="swiper-pagination" slot="pagination"></div>

      <!-- 輪播的導航器 -->
      <div class="swiper-button-prev" slot="button-prev"></div>
      <div class="swiper-button-next" slot="button-next"></div>
    </swiper>

  </div>
</template>
<script>
  // 引入 Swiper JS
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
          // 輪播的選項
          loop: true, // 循環播放
          pagination: {
            el: '.swiper-pagination', // 分頁器的 class 名稱
          },
          navigation: {
            nextEl: '.swiper-button-next', // 下一張按鈕的 class 名稱
            prevEl: '.swiper-button-prev', // 上一張按鈕的 class 名稱
          },
        },
      };
    },
    methods: {
      onSlideChange() {
        // 當 Slide 改變時的事件處理器
        console.log('當前 Slide:', this.$refs.mySwiper.swiper.realIndex);
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