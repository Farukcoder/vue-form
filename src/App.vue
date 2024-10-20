<template>
  <div class="container">
    <button @click="componentToRender='HomePage'">Home</button>
    <button @click="componentToRender='ContactPage'">Contact</button>
    <button @click="componentToRender='AboutPage'">About</button>
    <keep-alive>
      <component :is="componentToRender"></component>
    </keep-alive>
  </div>
</template>

<script>
import HomePage from "./components/HomePage.vue";
import AboutPage from "./components/AboutPage.vue";
import ContactPage from "./components/ContactPage.vue";

export default {
  data() {
    return {
      componentToRender: "HomePage"  // default component
    };
  },
  components: {
    HomePage,
    AboutPage,
    ContactPage
  }
};
</script>
