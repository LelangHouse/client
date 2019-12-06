<template>
  <div>
    <LoginRegisterpage @set-login="setLogin"></LoginRegisterpage>
    <MainPage></MainPage>
  </div>
</template>

<script>
import LoginRegisterpage from "./views/LoginRegisterpage";
import MainPage from "./views/MainPage";
export default {
  components: {
    LoginRegisterpage, MainPage
  },
  methods: {
    setLogin() {
      console.log("login sampai app.vue");
    }
  }
}
</script>

<style></style>