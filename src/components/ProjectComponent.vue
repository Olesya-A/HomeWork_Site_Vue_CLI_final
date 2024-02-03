<template>
  <HeaderComponent />
  <div class="project_banner">
    <div class="project_banner__intro">
      <h2 class="project_banner__intro_header">Our Project</h2>
      <p class="project_banner__intro_text">Home / Project</p>
    </div>
  </div>
  <div class="content center">
    <div class="content__categories">
      <button
        class="content__categories_button"
        v-for="item in categories"
        :key="item.id"
        @click="chooseProject(item.tag)"
      >
        {{ item.tag }}
      </button>
    </div>
    <div class="content__project">
      <div
        class="content__project_article"
        v-for="item in tempProject"
        :key="item.id"
      >
        <img :src="item.image" alt="image" />
        <svg
          @click="addFavourite($event)"
          class="content__project_article_svg"
          xmlns="http://www.w3.org/2000/svg"
          width="36"
          height="35"
          viewBox="0 0 36 35"
          fill="#fff"
        >
          <g filter="url(#filter0_d_993_156)">
            <path
              d="M16.0992 1.80951C16.7004 -0.0279021 19.2996 -0.0279021 19.9008 1.80951L21.7983 7.60879C22.0673 8.43084 22.8342 8.98685 23.6992 8.98685H29.8097C31.7506 8.98685 32.5539 11.4732 30.98 12.6088L26.0604 16.1581C25.3546 16.6674 25.0591 17.5748 25.3298 18.402L27.2146 24.1623C27.8166 26.0025 25.7137 27.539 24.1435 26.4062L19.1702 22.818C18.4715 22.3139 17.5285 22.3139 16.8298 22.818L11.8565 26.4062C10.2863 27.539 8.18335 26.0025 8.78545 24.1623L10.6702 18.402C10.9409 17.5748 10.6454 16.6674 9.93955 16.1581L5.02004 12.6088C3.44611 11.4732 4.24942 8.98685 6.19025 8.98685H12.3008C13.1658 8.98685 13.9327 8.43084 14.2017 7.60879L16.0992 1.80951Z"
              fill="#FFA928"
            />
          </g>
        </svg>
        <div class="content__project_article_wrapper">
          <div class="content__project_article_txt">
            <h3 class="content__project_article_txt_header">
              {{ item.heading }}
            </h3>
            <p class="content__project_article_txt_nav">{{ item.text }}</p>
          </div>
          <router-link :to="{ name: 'ProjectDetails', params: { id: index } }">
            <svg
              class="arrow"
              xmlns="http://www.w3.org/2000/svg"
              width="70"
              height="70"
              viewBox="0 0 70 70"
              fill="none"
            >
              <circle cx="35" cy="35" r="35" fill="#F4F0EC" />
              <path
                d="M32 44L40 35L32 26"
                stroke="#292F36"
                stroke-width="2"
                stroke-linecap="round"
                stroke-linejoin="round"
              /></svg
          ></router-link>
        </div>
      </div>
    </div>
    <PaginationComponent />
  </div>
  <FooterComponent />
</template>

<script>
import FooterComponent from "./FooterComponent.vue";
import HeaderComponent from "./HeaderComponent.vue";
import PaginationComponent from "./PaginationComponent.vue";

export default {
  data() {
    return {
      categories: [
        {
          id: 1,
          tag: "Bathroom",
        },
        {
          id: 2,
          tag: "Bedroom",
        },
        {
          id: 3,
          tag: "Kitchan",
        },
        {
          id: 4,
          tag: "Living Area",
        },
      ],
      projects: [
        {
          id: 1,
          tag: "Bedroom",
          image: require("@/assets/image/bedroom_1.jpg"),
          heading: "Minimal Bedroom",
          text: "Decor / Artchitecture",
        },
        {
          id: 2,
          tag: "Bedroom",
          image: require("@/assets/image/bedroom_2.jpg"),
          heading: "Classic Minimal Bedroom",
          text: "Decor / Artchitecture",
        },
        {
          id: 3,
          tag: "Bedroom",
          image: require("@/assets/image/bedroom_3.jpg"),
          heading: "Minimal Bedroom table",
          text: "Decor / Artchitecture",
        },
        {
          id: 4,
          tag: "Bedroom",
          image: require("@/assets/image/bedroom_4.jpg"),
          heading: "Modern Medroom",
          text: "Decor / Artchitecture",
        },
        {
          id: 5,
          tag: "Bedroom",
          image: require("@/assets/image/bedroom_5.jpg"),
          heading: "Minimal Bedroom",
          text: "Decor / Artchitecture",
        },
        {
          id: 6,
          tag: "Bedroom",
          image: require("@/assets/image/bedroom_6.jpg"),
          heading: "Modern Bedroom",
          text: "Decor / Artchitecture",
        },
        {
          id: 7,
          tag: "Bedroom",
          image: require("@/assets/image/bedroom_7.jpg"),
          heading: "System Table",
          text: "Decor / Artchitecture",
        },
        {
          id: 8,
          tag: "Bedroom",
          image: require("@/assets/image/bedroom_8.jpg"),
          heading: "Modern Bedroom",
          text: "Decor / Artchitecture",
        },
        {
          id: 9,
          tag: "Bathroom",
          image: require("@/assets/image/bathroom_1.jpg"),
          heading: "Modern bathroom",
          text: "Decor / Artchitecture",
        },
        {
          id: 10,
          tag: "Bathroom",
          image: require("@/assets/image/bathroom_2.jpg"),
          heading: "Modern bathroom",
          text: "Decor / Artchitecture",
        },
        {
          id: 11,
          tag: "Bathroom",
          image: require("@/assets/image/bathroom_3.jpg"),
          heading: "Modern bathroom",
          text: "Decor / Artchitecture",
        },
        {
          id: 12,
          tag: "Bathroom",
          image: require("@/assets/image/bathroom_5.jpg"),
          heading: "Modern bathroom",
          text: "Decor / Artchitecture",
        },
        {
          id: 13,
          tag: "Bathroom",
          image: require("@/assets/image/bathroom_4.jpg"),
          heading: "Modern bathroom",
          text: "Decor / Artchitecture",
        },
        {
          id: 14,
          tag: "Bathroom",
          image: require("@/assets/image/bathroom_1.jpg"),
          heading: "Modern bathroom",
          text: "Decor / Artchitecture",
        },
        {
          id: 15,
          tag: "Bathroom",
          image: require("@/assets/image/bathroom_2.jpg"),
          heading: "Modern bathroom",
          text: "Decor / Artchitecture",
        },
        {
          id: 16,
          tag: "Bathroom",
          image: require("@/assets/image/bathroom_3.jpg"),
          heading: "Modern bathroom",
          text: "Decor / Artchitecture",
        },
        {
          id: 17,
          tag: "Kitchan",
          image: require("@/assets/image/kitchen_1.jpg"),
          heading: "Minimal Kitchan",
          text: "Decor / Artchitecture",
        },
        {
          id: 18,
          tag: "Kitchan",
          image: require("@/assets/image/blog_item_4.jpg"),
          heading: "Minimal Kitchan",
          text: "Decor / Artchitecture",
        },
        {
          id: 19,
          tag: "Kitchan",
          image: require("@/assets/image/kitchen_2.jpg"),
          heading: "Minimal Kitchan",
          text: "Decor / Artchitecture",
        },
        {
          id: 20,
          tag: "Kitchan",
          image: require("@/assets/image/details_5_2.jpg"),
          heading: "Minimal Kitchan",
          text: "Decor / Artchitecture",
        },
        {
          id: 21,
          tag: "Kitchan",
          image: require("@/assets/image/blog_item_1.jpg"),
          heading: "Minimal Kitchan",
          text: "Decor / Artchitecture",
        },
        {
          id: 22,
          tag: "Kitchan",
          image: require("@/assets/image/kitchen_3.jpg"),
          heading: "Minimal Kitchan",
          text: "Decor / Artchitecture",
        },
        {
          id: 23,
          tag: "Kitchan",
          image: require("@/assets/image/blog_item_3.jpg"),
          heading: "Minimal Kitchan",
          text: "Decor / Artchitecture",
        },
        {
          id: 24,
          tag: "Kitchan",
          image: require("@/assets/image/blog_item_2.jpg"),
          heading: "Minimal Kitchan",
          text: "Decor / Artchitecture",
        },
        {
          id: 25,
          tag: "Living Area",
          image: require("@/assets/image/living_1.jpg"),
          heading: "Classic Living Area",
          text: "Decor / Artchitecture",
        },
        {
          id: 26,
          tag: "Living Area",
          image: require("@/assets/image/living_2.jpg"),
          heading: "Classic Living Area",
          text: "Decor / Artchitecture",
        },
        {
          id: 27,
          tag: "Living Area",
          image: require("@/assets/image/living_3.jpg"),
          heading: "Classic Living Area",
          text: "Decor / Artchitecture",
        },
        {
          id: 28,
          tag: "Living Area",
          image: require("@/assets/image/living_5.jpg"),
          heading: "Classic Living Area",
          text: "Decor / Artchitecture",
        },
        {
          id: 29,
          tag: "Living Area",
          image: require("@/assets/image/living_4.jpg"),
          heading: "Classic Living Area",
          text: "Decor / Artchitecture",
        },
        {
          id: 30,
          tag: "Living Area",
          image: require("@/assets/image/living_1.jpg"),
          heading: "Classic Living Area",
          text: "Decor / Artchitecture",
        },
        {
          id: 31,
          tag: "Living Area",
          image: require("@/assets/image/living_2.jpg"),
          heading: "Classic Living Area",
          text: "Decor / Artchitecture",
        },
        {
          id: 32,
          tag: "Living Area",
          image: require("@/assets/image/living_3.jpg"),
          heading: "Classic Living Area",
          text: "Decor / Artchitecture",
        },
      ],
      tempProject: [
        {
          id: 1,
          tag: "Bedroom",
          image: require("@/assets/image/bedroom_1.jpg"),
          heading: "Minimal Bedroom",
          text: "Decor / Artchitecture",
        },
        {
          id: 2,
          tag: "Bedroom",
          image: require("@/assets/image/bedroom_2.jpg"),
          heading: "Classic Minimal Bedroom",
          text: "Decor / Artchitecture",
        },
        {
          id: 3,
          tag: "Bedroom",
          image: require("@/assets/image/bedroom_3.jpg"),
          heading: "Minimal Bedroom table",
          text: "Decor / Artchitecture",
        },
        {
          id: 4,
          tag: "Bedroom",
          image: require("@/assets/image/bedroom_4.jpg"),
          heading: "Modern Medroom",
          text: "Decor / Artchitecture",
        },
        {
          id: 5,
          tag: "Bedroom",
          image: require("@/assets/image/bedroom_5.jpg"),
          heading: "Minimal Bedroom",
          text: "Decor / Artchitecture",
        },
        {
          id: 6,
          tag: "Bedroom",
          image: require("@/assets/image/bedroom_6.jpg"),
          heading: "Modern Bedroom",
          text: "Decor / Artchitecture",
        },
        {
          id: 7,
          tag: "Bedroom",
          image: require("@/assets/image/bedroom_7.jpg"),
          heading: "System Table",
          text: "Decor / Artchitecture",
        },
        {
          id: 8,
          tag: "Bedroom",
          image: require("@/assets/image/bedroom_8.jpg"),
          heading: "Modern Bedroom",
          text: "Decor / Artchitecture",
        },
      ],
      flag: false,
    };
  },
  methods: {
    chooseProject(tag) {
      this.tempProject = this.projects.filter((el) => el.tag === tag);
    },
    addFavourite(event) {
      this.flag = !this.flag;
      if (this.flag) {
        event.target.style.fill = "#FFA928";
      } else {
        event.target.style.fill = "#FFf";
      }
    },
  },
  components: { HeaderComponent, FooterComponent, PaginationComponent },
};
</script>

<style lang="scss" scoped></style>
