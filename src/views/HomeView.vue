<template>
  <div class="home">
    <img alt="Churras logo" src="../assets/logo192.png" />
    <HelloWorld msg="Churrascômetro" />
  </div>
</template>

<script>
// @ is an alias to /src
import HelloWorld from "@/components/HelloWorld.vue";

export default {
  name: "HomeView",
  components: {
    HelloWorld,
  },
};
</script>
<style>
img {
  padding: 5vh 5vw;
}
</style>
