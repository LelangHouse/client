<template>
  <div>
    <div class="container mt-5">
      <div class="card-columns">
        <ProductCard
          v-for="(data, index) in property"
          :key=index
          :databapak=data
        ></ProductCard>
      </div>
    </div>
    <div :show-update-modal="updateBid">
      <SubmitBidModal></SubmitBidModal>
    </div>
  </div>
</template>

<script>
import axios from "axios";
import ProductCard from "../components/ProductCard";
import SubmitBidModal from "../components/SubmitBidModal"

export default {
  name: "MainPage",
  data() {
    return {
      property: []
    };
  },
  components: {
    ProductCard, SubmitBidModal
  },
  // props: ["PropertyData"],
  methods: {
    getProperty() {
      axios({
        method: "GET",
        url: "http://localhost:3000/products" //belum ditambahi headers
      })
        .then(({ data }) => {
          // console.log(data);
          this.property = data;
        })
        .catch(err => {
          console.log(err);
        });
    },
    updateBid(){

    }
  },
  created() {
    this.getProperty(); // belum ditambah localstorage getItem
  }
};
</script>

<style></style>
