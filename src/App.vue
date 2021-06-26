<template>
<div>
  <Alert />
  <Form />
</div>
</template>

<script>
import Form from "./components/Form.vue";
import Alert from "./components/Alert.vue";

export default {
  name: "App",
  components: { Form, Alert },
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
