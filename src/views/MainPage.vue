<template>
  <div>
    <navbarZ></navbarZ>
    <formUpload @fetch-data-again="getProperty"></formUpload>

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
import navbarZ from "../components/Navbar"
import ProductCard from "../components/ProductCard";
import SubmitBidModal from "../components/SubmitBidModal";
import formUpload from "../components/formUpload"

export default {
  name: "MainPage",
  data() {
    return {
      property: [],
      biddingData: null
    };
  },
  components: {
    navbarZ,
    ProductCard,
    SubmitBidModal,
    formUpload
  },
  // props: ["PropertyData"],
  methods: {
    getProperty() {
      console.log('=========', localStorage.getItem("token"));
      axios({
        method: "GET",
        url: "http://localhost:3000/products",
        headers: { token: localStorage.getItem("token") }
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
    if (localStorage.getItem("token")) {
      this.getProperty();
    }
  }
};
</script>

<style></style>
