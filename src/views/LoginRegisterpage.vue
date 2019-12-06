<template>
  <div class="VideoBg box" id="loginPage">
    <video
      autoplay="autoplay"
      loop="loop"
      muted="muted"
      style="width: auto; height: 100%; visibility: visible;"
    >
      <source
        src="https://static.videezy.com/system/resources/previews/000/007/790/original/4K_UHD_Drone_Bellingham_Washington_Neighborhood_Reavealing__Fernando.mp4"
        type="video/mp4"
      />
    </video>
    <div class="VideoBg__content d-flex justify-content-center align-items-center">
      <LoginRegisterForm class="card d-flex mx-auto border-0" @set-login="setLogin"></LoginRegisterForm>
    </div>
  </div>
</template>

<script>
import LoginRegisterForm from "../components/LoginRegisterForm";
export default {
  name: "LoginRegisterpage",
  components: {
    LoginRegisterForm
  },
  methods: {
    setLogin() {
      this.$emit("set-login");
    }
  }
};
</script>

<style scoped>
#loginPage {
  width: 100vw;
  height: 100vh;
  /* background: url('https://images.unsplash.com/photo-1480074568708-e7b720bb3f09?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9') no-repeat center center fixed; */
  -webkit-background-size: cover;
  -moz-background-size: cover;
  -o-background-size: cover;
  background-size: cover;
}

.card {
  width: 300px;
  opacity: 0.9;
}

.VideoBg video {
  position: absolute;
  top: 50%;
  left: 50%;
  visibility: hidden;
  -webkit-transform: translate(-50%, -50%);
  transform: translate(-50%, -50%);
}

.box {
  height: 100vh;
  position: relative;
  background: url();
  background-size: contain;
  background-position: top;
  background-attachment: fixed;
  overflow: hidden;
}
.VideoBg__content {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
}
</style>