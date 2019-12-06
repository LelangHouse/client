<template>
  <div>
    <LoginRegisterpage @set-login="setLogin" v-show="!isLogin"></LoginRegisterpage>
    <MainPage v-show="isLogin"></MainPage>
  </div>
</template>

<script>
import LoginRegisterpage from "./views/LoginRegisterpage";
import MainPage from "./views/MainPage";
export default {
  data() {
    return {
      isLogin: false
    };
  },
  components: {
    LoginRegisterpage,
    MainPage
  },
  methods: {
    setLogin() {
      this.isLogin = true;
    }
  }
};
</script>

<style></style>