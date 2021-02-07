<template>
  <div class="login">
    <h1>This is an login page</h1>
    <div>
      <input type="text" v-model="username" />
      <input type="password" v-model="password" />
    </div>
    <div>
      <button @click="login">login</button>
      <div v-if="success">ログインに成功しました</div>
      <div v-else>ログインしていません</div>
    </div>
  </div>
</template>

<script>
import axios from "axios";
export default {
  name: "login",
  data() {
    return {
      username: "",
      password: "",
      success: null
    };
  },
  methods: {
    login() {
      axios
        .post("/api/login", {
          username: this.username,
          password: this.password
        })
        .then(() => {
          this.success = true;
        });
    }
  }
};
</script>
