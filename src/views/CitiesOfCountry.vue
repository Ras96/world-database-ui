<template>
  <div>
    <h2>{{ countryName }}の都市一覧</h2>
    <li v-for="city in cities" :key="city">
      <router-link :to="`/city/${city}`">
        {{ city }}
      </router-link>
    </li>
  </div>
</template>

<script>
import axios from "axios";
export default {
  name: "city",
  data() {
    return {
      countryName: "",
      cities: null
    };
  },
  mounted() {
    const countryName = this.$route.params.countryName;
    this.countryName = countryName;
    axios.get("/api/countries/" + countryName).then(res => {
      this.cities = res.data;
    });
  }
};
</script>
