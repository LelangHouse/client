<template>
  <div>
    <div class="card mt-3">
      <img
        class="card-img-top"
        alt="Card image cap"
        :src=databapak.image
        width="100px"
      />
      <div class="card-body">
        <h3 class="card-title">{{ databapak.bid }}</h3>
        <div class="row mb-2">
          <div class="col-sm-6">Offered Price</div>
          <div class="col-sm-6">{{ databapak.price }} IDR</div>
        </div>
        <div class="row mb-2">
          <div class="col-sm-6">Bid</div>
          <div class="col-sm-6">{{ databapak.bid }} IDR</div>
        </div>
      </div>
      <a href="#" style="text-decoration: none"
        ><b-button @click.prevent="UpdateBidModal()" v-b-modal.modal-1 type="button" class="btn btn-info btn-lg btn-block">
          Submit a Bid
        </b-button></a>
    </div>
  </div>
</template>

<script>
export default {
  props: ["databapak"],
  methods: {
    UpdateBidModal(data){
      this.$emit('show-update-modal', this.databapak)
    }
  }
};
</script>

<style></style>
