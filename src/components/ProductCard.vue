<template>
  <div>
    <div class="card mt-3" style="border-radius: 5px">
      <img
        class="card-img-top"
        alt="Card image cap"
        :src="databapak.image"
        width="100px"
      />
      <div class="card-body">
        <h3 class="card-title">{{ databapak.bid }} IDR</h3>
        <div class="row">
          <div class="col-sm-6">Offered Price</div>
          <div class="col-sm-6">{{ databapak.price }} IDR</div>
        </div>
      </div>

      <div class="container">
        <b-button
          @click="UpdateBidModal"
          type="button"
          class="btn btn-info btn-lg btn-block"
        >
          Bid
        </b-button>
      </div>
      <div class="container mt-2 mb-2">
        <b-row>
          <b-col
            ><b-button
              @click="shareWa"
              type="button"
              class="btn btn-info btn-lg btn-block"
            >
              <i class="fab fa-whatsapp"></i>
              </b-col>
          <b-col
            ><b-button
              type="button"
              class="btn btn-info btn-lg btn-block"
            >
              <i class="fab fa-facebook-f"></i>
            </b-button></b-col
          >
        </b-row>
      </div>
    </div>
  </div>
</template>

<script>
import axios from 'axios'

export default {
  props: ["databapak"],
  component: {},
  methods: {
    UpdateBidModal() {
      this.$emit("show-update-modal", this.databapak);
    },
    shareWa(){
      axios({
        url: "http://localhost:3000/products/shareWa",
        method: "POST",
        headers: {
          token: localStorage.getItem('token')
        },
        data: {
         url : `${this.databapak.image}`
        }
      })
      .then(data=>{
        console.log(data)
      })
      .catch(err=>{
        console.log(err)
      })
    }
  }
};
</script>
<style scoped>
  button {
    border-radius: 0px;
  }
</style>
