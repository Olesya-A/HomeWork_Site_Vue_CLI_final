<template>
  <div class="swiper_div center">
    <swiper
      :style="{
        '--swiper-navigation-color': '#fff',
        '--swiper-pagination-color': '#fff',
      }"
      :zoom="true"
      :navigation="true"
      :pagination="{
        clickable: true,
      }"
      :modules="modules"
      class="mySwiper"
    >
      <swiper-slide>
        <div class="swiper-zoom-container">
          <img :src="image1" alt="" />
        </div>
      </swiper-slide>
      <swiper-slide>
        <div class="swiper-zoom-container">
          <img :src="image2" alt="" />
        </div>
      </swiper-slide>
      <swiper-slide>
        <div class="swiper-zoom-container">
          <img :src="image3" alt="" />
        </div>
      </swiper-slide>
    </swiper>
  </div>
</template>

<script>
import { Swiper, SwiperSlide } from "swiper/vue";

import "swiper/css";

import "swiper/css/zoom";
import "swiper/css/navigation";
import "swiper/css/pagination";

import { Zoom, Navigation, Pagination } from "swiper/modules";

export default {
  components: {
    Swiper,
    SwiperSlide,
  },
  data() {
    return {
      image1: require("@/assets/image/project_details_1.jpg"),
      image2: require("@/assets/image/project_details_2.jpg"),
      image3: require("@/assets/image/project_details_3.jpg"),
    };
  },
  setup() {
    return {
      modules: [Zoom, Navigation, Pagination],
    };
  },
};
</script>

<style lang="scss" scoped>
body {
  position: relative;
  height: 100%;
}

.swiper_div {
  margin-bottom: 200px;
}

.swiper {
  width: 100%;
  height: 100%;
}

.swiper-slide {
  overflow: hidden;
}
.swiper-zoom-container {
  width: 1200px;
  height: 799px;

  & img {
    width: 100%;
    object-fit: cover;
    border-radius: 70px;
  }
}
</style>
