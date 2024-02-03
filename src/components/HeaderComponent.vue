<template>
  <header class="header center">
    <div class="header__left" href="main.html">
      <svg
        xmlns="http://www.w3.org/2000/svg"
        width="34"
        height="34"
        viewBox="0 0 34 34"
        fill="none"
      >
        <path
          d="M0 34.0003H13.4588V24.499C13.4588 22.4853 15.0898 20.8543 17.1035 20.8543C19.1172 20.8543 20.7482 22.4853 20.7482 24.499V34.0003H33.9975V0C15.2211 0 0 15.2211 0 34.0003Z"
          fill="#CDA274"
        />
      </svg>
      <h3 class="header__left_title">Interno</h3>
    </div>
    <nav class="header__right">
      <router-link
        class="header__right_nav"
        v-for="link in links"
        :key="link.id"
        :to="link.url"
        >{{ link.name }}</router-link
      >
      <!--       <a href="#" class="header__right_nav">Home</a>
      <a href="#" class="header__right_nav">Project</a>
      <a href="#" class="header__right_nav">Blog</a> -->
    </nav>
  </header>
</template>

<script>
export default {
  data() {
    return {
      links: [
        {
          id: 0,
          name: "Home",
          url: "/",
        },
        {
          id: 1,
          name: "Project",
          url: "/project",
        },
        {
          id: 0,
          name: "Blog",
          url: "/blog",
        },
      ],
    };
  },
};
</script>

<style lang="scss" scoped></style>
