<template>
  <HeaderComponent />
  <div class="details_banner center"></div>
  <div class="articles center">
    <div class="articles__details">
      <div
        class="articles__details_article"
        v-for="item in temp"
        :key="item.id"
      >
        <h2 class="articles__details_article_header">{{ item.header1 }}</h2>
        <img
          :src="item.image1"
          class="articles__details_article_image1"
          alt="image"
        />
        <div class="articles__details_article_wrapper">
          <p>{{ item.date }}</p>
          <p>{{ item.nav }}</p>
        </div>
        <p class="articles__details_article_text">{{ item.text1 }}</p>
        <p class="articles__details_article_text">{{ item.text2 }}</p>
        <div class="articles__details_article_slogan">
          <img :src="item.commas" alt="commas" />
          <h1 class="articles__details_article_slogan_header">
            {{ item.slogan }}
          </h1>
        </div>
        <h2 class="articles__details_article_header">{{ item.header2 }}</h2>
        <p class="articles__details_article_text">{{ item.text3 }}</p>
        <ol class="articles__details_article_ol">
          <li class="articles__details_article_li">{{ item.list2 }}</li>
          <li class="articles__details_article_li">{{ item.list1 }}</li>
          <li class="articles__details_article_li">{{ item.list3 }}</li>
        </ol>
        <img
          :src="item.image2"
          class="articles__details_article_image2"
          alt="image"
        />
        <p class="articles__details_article_text">{{ item.text4 }}</p>
      </div>
    </div>
    <div class="articles__sidebar">
      <h3 class="articles__sidebar_header">Tags</h3>
      <div class="articles__sidebar_tags">
        <button
          class="articles__sidebar_tags_button"
          v-for="item in tags"
          :key="item.id"
          @click="chooseArticle(item.id)"
        >
          {{ item.tagName }}
        </button>
      </div>
    </div>
  </div>
  <FooterComponent />
</template>

<script>
import FooterComponent from "./FooterComponent.vue";
import HeaderComponent from "./HeaderComponent.vue";

export default {
  data() {
    return {
      details: [
        {
          id: 1,
          header1: "Let’s Get Solution for Building Construction Work",
          image1: require("@/assets/image/details_1_1.jpg"),
          date: "26 December,2022 ",
          nav: "Interior / Home / Decore",
          text1:
            "Lorem ipsum dolor sit amet, adipiscing Aliquam eu sem vitae turpmaximus.posuere in.Contrary to popular belief.There are many variations of passages of Lorem Ipsum available, but the majority have suffered alteration in some form, by injecthumour, or randomised words which don't look even slightly believable.",
          text2:
            "Embarrassing hidden in the middle of text. All the Lorem Ipsum generators on the Internet tend to repeat predefined chunks as necessary.",
          commas: require("@/assets/image/details_commas.png"),
          slogan: "The details are not the details. They make the design.",
          header2: "Design sprints are great",
          text3:
            "Lorem ipsum dolor sit amet, adipiscing Aliquam eu sem vitae turpmaximus.posuere in.Contrary to popular belief.There are many variations of passages of Lorem Ipsum available, but the majority have suffered.",
          list1:
            "Contrary to popular belief.There are many variations of passages of Lorem Ipsum available, but the majority have suffered.",
          list2:
            "Contrary to popular belief.There are many variations of passages of Lorem Ipsum available, but the majority have suffered.",
          list3:
            "Contrary to popular belief.There are many variations of passages of Lorem Ipsum available, but the majority have suffered.",
          image2: require("@/assets/image/details_1_2.jpg"),
          text4:
            "Lorem ipsum dolor sit amet, adipiscing Aliquam eu sem vitae turpmaximus.posuere in.Contrary to popular belief.There are many variations of passages of Lorem Ipsum available, but the majority have suffered.",
        },
        {
          id: 2,
          header1: "Low Cost Latest Invented Interior Designing Ideas.",
          image1: require("@/assets/image/details_2_1.jpg"),
          date: "22 December,2022 ",
          nav: "Interior / Home / Decore",
          text1:
            "Lorem ipsum dolor sit amet, adipiscing Aliquam eu sem vitae turpmaximus.posuere in.Contrary to popular belief.There are many variations of passages of Lorem Ipsum available, but the majority have suffered alteration in some form, by injecthumour, or randomised words which don't look even slightly believable.",
          text2:
            "Embarrassing hidden in the middle of text. All the Lorem Ipsum generators on the Internet tend to repeat predefined chunks as necessary.",
          commas: require("@/assets/image/details_commas.png"),
          slogan: "The details are not the details. They make the design.",
          header2: "Design sprints are great",
          text3:
            "Lorem ipsum dolor sit amet, adipiscing Aliquam eu sem vitae turpmaximus.posuere in.Contrary to popular belief.There are many variations of passages of Lorem Ipsum available, but the majority have suffered.",
          list1:
            "Contrary to popular belief.There are many variations of passages of Lorem Ipsum available, but the majority have suffered.",
          list2:
            "Contrary to popular belief.There are many variations of passages of Lorem Ipsum available, but the majority have suffered.",
          list3:
            "Contrary to popular belief.There are many variations of passages of Lorem Ipsum available, but the majority have suffered.",
          image2: require("@/assets/image/details_2_2.jpg"),
          text4:
            "Lorem ipsum dolor sit amet, adipiscing Aliquam eu sem vitae turpmaximus.posuere in.Contrary to popular belief.There are many variations of passages of Lorem Ipsum available, but the majority have suffered.",
        },
        {
          id: 3,
          header1: "Best For Any Office & Business Interior Solution",
          image1: require("@/assets/image/details_3_1.jpg"),
          date: "25 December,2022 ",
          nav: "Interior / Home / Decore",
          text1:
            "Lorem ipsum dolor sit amet, adipiscing Aliquam eu sem vitae turpmaximus.posuere in.Contrary to popular belief.There are many variations of passages of Lorem Ipsum available, but the majority have suffered alteration in some form, by injecthumour, or randomised words which don't look even slightly believable.",
          text2:
            "Embarrassing hidden in the middle of text. All the Lorem Ipsum generators on the Internet tend to repeat predefined chunks as necessary.",
          commas: require("@/assets/image/details_commas.png"),
          slogan: "The details are not the details. They make the design.",
          header2: "Design sprints are great",
          text3:
            "Lorem ipsum dolor sit amet, adipiscing Aliquam eu sem vitae turpmaximus.posuere in.Contrary to popular belief.There are many variations of passages of Lorem Ipsum available, but the majority have suffered.",
          list1:
            "Contrary to popular belief.There are many variations of passages of Lorem Ipsum available, but the majority have suffered.",
          list2:
            "Contrary to popular belief.There are many variations of passages of Lorem Ipsum available, but the majority have suffered.",
          list3:
            "Contrary to popular belief.There are many variations of passages of Lorem Ipsum available, but the majority have suffered.",
          image2: require("@/assets/image/details_3_2.jpg"),
          text4:
            "Lorem ipsum dolor sit amet, adipiscing Aliquam eu sem vitae turpmaximus.posuere in.Contrary to popular belief.There are many variations of passages of Lorem Ipsum available, but the majority have suffered.",
        },
        {
          id: 4,
          header1: "Let’s Get Solution for Building Construction Work",
          image1: require("@/assets/image/details_4_1.jpg"),
          date: "26 December,2022 ",
          nav: "Interior / Home / Decore",
          text1:
            "Lorem ipsum dolor sit amet, adipiscing Aliquam eu sem vitae turpmaximus.posuere in.Contrary to popular belief.There are many variations of passages of Lorem Ipsum available, but the majority have suffered alteration in some form, by injecthumour, or randomised words which don't look even slightly believable.",
          text2:
            "Embarrassing hidden in the middle of text. All the Lorem Ipsum generators on the Internet tend to repeat predefined chunks as necessary.",
          commas: require("@/assets/image/details_commas.png"),
          slogan: "The details are not the details. They make the design.",
          header2: "Design sprints are great",
          text3:
            "Lorem ipsum dolor sit amet, adipiscing Aliquam eu sem vitae turpmaximus.posuere in.Contrary to popular belief.There are many variations of passages of Lorem Ipsum available, but the majority have suffered.",
          list1:
            "Contrary to popular belief.There are many variations of passages of Lorem Ipsum available, but the majority have suffered.",
          list2:
            "Contrary to popular belief.There are many variations of passages of Lorem Ipsum available, but the majority have suffered.",
          list3:
            "Contrary to popular belief.There are many variations of passages of Lorem Ipsum available, but the majority have suffered.",
          image2: require("@/assets/image/details_4_2.jpg"),
          text4:
            "Lorem ipsum dolor sit amet, adipiscing Aliquam eu sem vitae turpmaximus.posuere in.Contrary to popular belief.There are many variations of passages of Lorem Ipsum available, but the majority have suffered.",
        },
        {
          id: 5,
          header1: "Low Cost Latest Invented Interior Designing Ideas.",
          image1: require("@/assets/image/details_5_1.jpg"),
          date: "22 December,2022 ",
          nav: "Interior / Home / Decore",
          text1:
            "Lorem ipsum dolor sit amet, adipiscing Aliquam eu sem vitae turpmaximus.posuere in.Contrary to popular belief.There are many variations of passages of Lorem Ipsum available, but the majority have suffered alteration in some form, by injecthumour, or randomised words which don't look even slightly believable.",
          text2:
            "Embarrassing hidden in the middle of text. All the Lorem Ipsum generators on the Internet tend to repeat predefined chunks as necessary.",
          commas: require("@/assets/image/details_commas.png"),
          slogan: "The details are not the details. They make the design.",
          header2: "Design sprints are great",
          text3:
            "Lorem ipsum dolor sit amet, adipiscing Aliquam eu sem vitae turpmaximus.posuere in.Contrary to popular belief.There are many variations of passages of Lorem Ipsum available, but the majority have suffered.",
          list1:
            "Contrary to popular belief.There are many variations of passages of Lorem Ipsum available, but the majority have suffered.",
          list2:
            "Contrary to popular belief.There are many variations of passages of Lorem Ipsum available, but the majority have suffered.",
          list3:
            "Contrary to popular belief.There are many variations of passages of Lorem Ipsum available, but the majority have suffered.",
          image2: require("@/assets/image/details_5_2.jpg"),
          text4:
            "Lorem ipsum dolor sit amet, adipiscing Aliquam eu sem vitae turpmaximus.posuere in.Contrary to popular belief.There are many variations of passages of Lorem Ipsum available, but the majority have suffered.",
        },
        {
          id: 6,
          header1: "Best For Any Office & Business Interior Solution",
          image1: require("@/assets/image/details_6_1.jpg"),
          date: "25 December,2022 ",
          nav: "Interior / Home / Decore",
          text1:
            "Lorem ipsum dolor sit amet, adipiscing Aliquam eu sem vitae turpmaximus.posuere in.Contrary to popular belief.There are many variations of passages of Lorem Ipsum available, but the majority have suffered alteration in some form, by injecthumour, or randomised words which don't look even slightly believable.",
          text2:
            "Embarrassing hidden in the middle of text. All the Lorem Ipsum generators on the Internet tend to repeat predefined chunks as necessary.",
          commas: require("@/assets/image/details_commas.png"),
          slogan: "The details are not the details. They make the design.",
          header2: "Design sprints are great",
          text3:
            "Lorem ipsum dolor sit amet, adipiscing Aliquam eu sem vitae turpmaximus.posuere in.Contrary to popular belief.There are many variations of passages of Lorem Ipsum available, but the majority have suffered.",
          list1:
            "Contrary to popular belief.There are many variations of passages of Lorem Ipsum available, but the majority have suffered.",
          list2:
            "Contrary to popular belief.There are many variations of passages of Lorem Ipsum available, but the majority have suffered.",
          list3:
            "Contrary to popular belief.There are many variations of passages of Lorem Ipsum available, but the majority have suffered.",
          image2: require("@/assets/image/details_6_2.jpg"),
          text4:
            "Lorem ipsum dolor sit amet, adipiscing Aliquam eu sem vitae turpmaximus.posuere in.Contrary to popular belief.There are many variations of passages of Lorem Ipsum available, but the majority have suffered.",
        },
      ],
      tags: [
        {
          id: 1,
          tagName: "Kitchen",
        },
        {
          id: 2,
          tagName: "Bedroom",
        },
        {
          id: 3,
          tagName: "Building",
        },
        {
          id: 4,
          tagName: "Architecture",
        },
        {
          id: 5,
          tagName: "Kitchen Planning",
        },
        {
          id: 6,
          tagName: "Bedroom",
        },
      ],
      temp: [
        {
          id: 1,
          header1: "Let’s Get Solution for Building Construction Work",
          image1: require("@/assets/image/details_1_1.jpg"),
          date: "26 December,2022 ",
          nav: "Interior / Home / Decore",
          text1:
            "Lorem ipsum dolor sit amet, adipiscing Aliquam eu sem vitae turpmaximus.posuere in.Contrary to popular belief.There are many variations of passages of Lorem Ipsum available, but the majority have suffered alteration in some form, by injecthumour, or randomised words which don't look even slightly believable.",
          text2:
            "Embarrassing hidden in the middle of text. All the Lorem Ipsum generators on the Internet tend to repeat predefined chunks as necessary.",
          commas: require("@/assets/image/details_commas.png"),
          slogan: "The details are not the details. They make the design.",
          header2: "Design sprints are great",
          text3:
            "Lorem ipsum dolor sit amet, adipiscing Aliquam eu sem vitae turpmaximus.posuere in.Contrary to popular belief.There are many variations of passages of Lorem Ipsum available, but the majority have suffered.",
          list1:
            "Contrary to popular belief.There are many variations of passages of Lorem Ipsum available, but the majority have suffered.",
          list2:
            "Contrary to popular belief.There are many variations of passages of Lorem Ipsum available, but the majority have suffered.",
          list3:
            "Contrary to popular belief.There are many variations of passages of Lorem Ipsum available, but the majority have suffered.",
          image2: require("@/assets/image/details_1_2.jpg"),
          text4:
            "Lorem ipsum dolor sit amet, adipiscing Aliquam eu sem vitae turpmaximus.posuere in.Contrary to popular belief.There are many variations of passages of Lorem Ipsum available, but the majority have suffered.",
        },
      ],
    };
  },
  methods: {
    chooseArticle(id) {
      this.temp = this.details.filter((el) => el.id === id);
    },
  },
  components: { HeaderComponent, FooterComponent },
};
</script>

<style scoped lang="scss"></style>
