<template>
<div class="container">
  <!-- <Alert /> -->
  <nav class="nav nav-tabs justify-content-center">
    <a class="nav-link" href="#" v-for="tab in tabs" :key="tab" @click="selected = tab; ">{{tab}}</a>
  </nav>
  <component :is="selected"></component>
</div>
</template>

<script>
import Form from "./components/Form.vue";
import Alert from "./components/Alert.vue";
import Shop from "./components/Shop.vue";

export default {
  name: "App",
  data: function() {
    return {
      tabs: ["Shop", "Form", "Alert"],
      selected: "Shop"
    };
  },
  components: { Form, Alert, Shop },
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
