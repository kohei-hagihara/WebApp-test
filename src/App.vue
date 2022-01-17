<template>
  <div id="app">
    <a>現在{{ number }}回クリックされています</a>
    <button @click="countUp">カウントアップ</button>
    <!--<input type="text" v-model="message">
    <h1>{{message}}</h1>
    -->
  </div>
</template>

<script>
// import HelloWorld from "./components/HelloWorld";

export default {
  name: "App",
  components: {
    // HelloWorld
  },
  data() {
    return {
      number: 0,
      //message: 'こんにちは',
      //@24
    };
  },
  methods: {
    countUp: function () {
      this.number += 1;
      this.getIp();
    },
    getIp() {
      this.axios
        .get("http://192.168.1.76:9898/")
        .then((response) => console.log(response.data))
        .catch((error) => console.log(error));
    },
  },
};
</script>

<style>
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
