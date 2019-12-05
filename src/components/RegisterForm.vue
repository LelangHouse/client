<template>
  <div
    class="tab-pane fade show active"
    id="pills-register"
    role="tabpanel"
    aria-labelledby="pills-register-tab"
  >
    <form v-on:submit.prevent="register">
      <div class="form-group">
        <input
          type="text"
          name="username"
          id="name"
          class="form-control"
          placeholder="Username"
          v-model="username"
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
          v-model="email"
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
          v-model="phone"
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
          v-model="password"
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
import axios from "axios";
import Swal from "sweetalert2";

export default {
  name: "RegisterForm",
  data() {
    return {
      email: "",
      password: "",
      username: "",
      phone: ""
    };
  },
  methods: {
    register() {
      axios({
        url: "http://localhost:3000/users/register",
        method: "POST",
        data: {
          email: this.email,
          password: this.password,
          username: this.username,
          phone: this.phone
        }
      })
        .then(({ data }) => {
          localStorage.setItem("token", data.token);
          this.$emit("set-login");
          console.log(`register successful`);
          this.email = "";
          this.password = "";
          this.phone = "";
          this.username = "";
          Swal.fire({
            icon: "success",
            title: "Registration successful",
            showConfirmButton: false,
            timer: 1500
          });
        })
        .catch(err => {
          console.log(err);
          Swal.fire({
            icon: "error",
            title: "Oops...",
            text:
              "The email that you use is already registered in our database, please use other email.",
            footer: "<a href>Why do I have this issue?</a>"
          });
        });
    }
  }
};
</script>

<style>
</style>