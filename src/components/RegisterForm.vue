<template>
  <div
    class="tab-pane fade show active"
    id="pills-register"
    role="tabpanel"
    aria-labelledby="pills-register-tab"
  >
    <form>
      <div class="form-group">
        <input
          type="text"
          name="username"
          id="name"
          class="form-control"
          placeholder="Username"
          required
          autofocus
        />
      </div>

      <div class="form-group">
        <input
          type="email"
          name="email"
          id="email"
          class="form-control"
          placeholder="Email"
          required
        />
      </div>
      <div class="form-group">
        <input
          type="text"
          name="phone"
          id="phone"
          class="form-control"
          placeholder="Phone"
          required
        />
      </div>

      <div class="form-group">
        <input
          type="password"
          name="password"
          id="password"
          class="form-control"
          placeholder="Set a password"
          required
        />
      </div>

      <div class="text-center pt-2 pb-1">
        <button type="submit" class="btn btn-primary">Register</button>
      </div>
    </form>
  </div>
</template>

<script>
export default {
  name: "RegisterForm"
};
</script>

<style>
</style>