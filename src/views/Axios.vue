<template>
  <div>
    <button @click="sendGet">get</button>
    <button @click="sendPost">post</button>
    <button @click="sendPut">put</button>
    <button @click="sendDelete">delete</button>
  </div>
</template>

<script>
import axios from "axios";
export default {
  name: "Axios",
  methods: {
    sendGet() {
      axios.get("https://enjrsfnuktlw2sr.m.pipedream.net");
    },
    sendPost() {
      axios.post("https://enjrsfnuktlw2sr.m.pipedream.net", {
        traQID: "Ras",
        grade: 20
      });
    },
    sendPut() {
      axios.put("https://enjrsfnuktlw2sr.m.pipedream.net", {
        testData: { string: "string", number: 1 }
      });
    },
    sendDelete() {
      axios.delete("https://enjrsfnuktlw2sr.m.pipedream.net", {
        data: { po: 1 }
      });
    }
  }
};
</script>
