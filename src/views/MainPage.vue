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
        url: "http://localhost:3000/products",
        headers: { access_token: localStorage.getItem("access_token") }
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
    localStorage.setItem("access_token", user.access_token);
    this.getProperty();
  }
};
</script>

<style></style>
