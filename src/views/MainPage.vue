<template>
  <div>
    <div class="container mt-5">
      <div class="card-columns">
        <ProductCard
          v-for="(data, index) in property"
          :key="index"
          :databapak="data"
          @show-update-modal="updateBid"
        ></ProductCard>
      </div>
    </div>
    <div>
      <SubmitBidModal
        :bid-data="biddingData"
        @fetch-data-again="getProperty"
      ></SubmitBidModal>
    </div>
  </div>
</template>

<script>
import axios from "axios";
import ProductCard from "../components/ProductCard";
import SubmitBidModal from "../components/SubmitBidModal";

export default {
  name: "MainPage",
  data() {
    return {
      property: [],
      biddingData: null
    };
  },
  components: {
    ProductCard,
    SubmitBidModal
  },
  // props: ["PropertyData"],
  methods: {
    getProperty() {
      axios({
        method: "GET",
        url: "http://localhost:3000/products" //belum ditambahi headers
      })
        .then(({ data }) => {
          this.property = data;
        })
        .catch(err => {
          console.log(err);
        });
    },
    updateBid(databapak) {
      this.biddingData = databapak;
      this.$bvModal.show("modal-1");
    }
  },
  created() {
    this.getProperty(); // belum ditambah localstorage getItem
  }
};
</script>

<style></style>
