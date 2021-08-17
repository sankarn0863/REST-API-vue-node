<template>
  <div class="home">
    <img alt="Vue logo" src="../assets/logo.gif" height="300" width="auto">
    <HelloWorld msg="WELCOME TO DEMO PROJECT: WYVERN 04" />
  </div>
</template>

<script>
// @ is an alias to /src
import HelloWorld from "@/components/HelloWorld.vue";

export default {
  name: "Home",
  components: {
    HelloWorld,
  },
};
</script>
