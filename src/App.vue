<template>
  <div>
    <LoginRegisterpage @set-login="setLogin"></LoginRegisterpage>
  </div>
</template>

<script>
import LoginRegisterpage from "./views/LoginRegisterpage";
export default {
  components: {
    LoginRegisterpage
  },
  methods: {
    setLogin() {
      console.log("login sampai app.vue");
    }
  }
};
</script>

<style>
</style>