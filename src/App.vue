<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png">
    <SimpleForm initial-value="初期値だよ" @submit="onSubmit"/>
    <div v-if="msg" class="msg">
      SimpleForm から受け取った値は
      <strong>{{ msg }}</strong> です
    </div>
  </div>
</template>

<script>
import SimpleForm from "./components/SimpleForm.vue";

export default {
  name: "app",
  components: {
    SimpleForm
  },
  data() {
    return {
      msg: ""
    };
  },
  methods: {
    onSubmit(value) {
      this.msg = value;
    }
  }
};
</script>

<style lang="scss" scoped>
#app {
  font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Helvetica, Arial,
    sans-serif, "Apple Color Emoji", "Segoe UI Emoji", "Segoe UI Symbol";
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  max-width: 30rem;
  margin: 4rem auto 0;
}

.msg {
  margin: 2rem 2rem 0;
  padding-top: 2rem;
  border-top: 1px solid #efefef;
}
</style>
