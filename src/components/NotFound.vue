<template>
  <HeaderComponent />
  <div class="notfound">
    <div class="notfound-content">
      <h1 class="notfound-content__header">404</h1>
      <p class="notfound-content__text">
        We are sorry, but the page you requested was not found
      </p>
      <button class="notfound-content__button">
        <router-link class="button-link" :to="link.url"
          >Back To Home
          <svg
            width="19"
            height="17"
            viewBox="0 0 19 17"
            fill="none"
            xmlns="http://www.w3.org/2000/svg"
          >
            <path
              d="M2 8.43542L15.7232 8.29857M10.6182 1.91138L17.1412 8.43436L10.4868 15.0887"
              stroke="#CDA274"
              stroke-width="2"
              stroke-linecap="square"
              stroke-linejoin="round"
            /></svg
        ></router-link>
      </button>
    </div>
    <img
      class="notfound-img"
      src="../assets/image/not_found.jpg"
      alt="not found page"
    />
  </div>
</template>

<script>
import HeaderComponent from "./HeaderComponent.vue";

export default {
  data() {
    return {
      link: {
        name: "Home",
        url: "/",
      },
    };
  },
  components: { HeaderComponent },
};
</script>

<style lang="scss" scoped></style>
