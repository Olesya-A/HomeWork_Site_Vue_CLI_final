<template>
  <HeaderComponent />
  <div class="project_details_banner center"></div>
  <div class="project_details center">
    <h2 class="project_details_header">{{ projectDetails.header }}</h2>
    <p class="project_details_text">{{ projectDetails.text1 }}</p>
    <p class="project_details_text">{{ projectDetails.text2 }}</p>
  </div>
  <SliderComponent />
  <FooterComponent />
</template>

<script>
import FooterComponent from "./FooterComponent.vue";
import HeaderComponent from "./HeaderComponent.vue";
import SliderComponent from "./SliderComponent.vue";

import { mapState } from "vuex";

export default {
  data() {
    return {};
  },
  computed: {
    ...mapState(["projectDetails"]),
  },
  components: { HeaderComponent, FooterComponent, SliderComponent },
};
</script>

<style lang="scss" scoped></style>
