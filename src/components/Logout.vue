<template>
  <button type="button" class="btn btn-outline-danger" @click="logOut"> <i class="fa fa-sign-out" aria-hidden="true"></i> Log Out</button>
</template>

<script>

export default {
  name: "LogoutBtn",
  methods: {
    logOut() {
      localStorage.clear()
      this.$emit('logoutbapak')
    }
  }
};
</script>

<style>
</style>