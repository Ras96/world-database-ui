<template>
  <div>
    <h2>国一覧</h2>
    <li v-for="country in countries" :key="country">
      <router-link :to="`/country/${country}`">
        {{ country }}
      </router-link>
    </li>
  </div>
</template>

<script>
import axios from "axios";
export default {
  name: "Country",
  data() {
    return {
      countries: null
    };
  },
  mounted() {
    axios.get("/api/countries").then(res => {
      this.countries = res.data;
    });
  }
};
</script>
