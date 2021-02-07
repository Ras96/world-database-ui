<template>
  <div class="home">
    <img alt="Vue logo" src="../assets/logo.png" />
    <div>都市名を入力</div>
    <input type="text" v-model="cityName" />
    <button @click="getCityInfo">表示する</button>
    <HelloWorld msg="Welcome to Your Vue.js App" />
  </div>
</template>

<script>
// @ is an alias to /src
import HelloWorld from "@/components/HelloWorld.vue";

export default {
  name: "Home",
  components: {
    HelloWorld
  },
  methods: {
    getCityInfo() {
      const cityName = this.cityName;
      this.$router.push("/city/" + cityName);
    }
  }
};
</script>
