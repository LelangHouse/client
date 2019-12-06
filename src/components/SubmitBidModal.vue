<template>
  <div>
    <b-modal id="modal-1" title="Submit Bid" @ok="updateBid">
      <form>
        <b-input-group prepend="IDR" class="mb-2 mr-sm-2 mb-sm-0">
          <b-input
            v-model="newBid"
            type="number"
            id="inline-form-input-username"
            placeholder="Bid"
          ></b-input>
        </b-input-group>
      </form>
    </b-modal>
  </div>
</template>

<script>
import axios from "axios";
export default {
  props: ["bidData"],
  data() {
    return {
      newBid: null
    };
  },
  methods: {
    updateBid() {
      axios({
        method: "PUT",
        url: `http://localhost:3000/products/${this.bidData._id}`,
        data: {
          bid: this.newBid
        }
      })
        .then(result => {
          this.newBid = null;
          this.$emit("fetch-data-again");
        })
        .catch(err => {
          console.log(err);
        });
    }
  }
};
</script>

<style></style>
