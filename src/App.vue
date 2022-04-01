<template>
  <NavBar />
  <h1>Hello Pinia!</h1>
  <RouterView />
</template>

<script>
import NavBar from "./components/NavBar.vue";

export default {
  components: {
    NavBar,
  },
};
</script>
