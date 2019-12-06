<template>
  <div>
      <b-navbar toggleable="lg" type="dark" variant="info" >
        <b-nav-form>
          <b-button @click="logout" size="sm" class="my-2 my-sm-0" type="submit"><i class="fas fa-sign-out-alt"></i> Logout</b-button>
        </b-nav-form>
      </b-navbar>
  </div>
</template>

<script>
export default {
  name: "navbarZ",
  methods: {
    logout(){
      localStorage.removeItem('token')
      this.$emit('set-login', false)
    }
  }
}
</script>

<style>

</style>