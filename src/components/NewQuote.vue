<template>
  <div class="row">
    <div class="col-md-10 col-sm-12">
      <div class="addQuote">
        <label>Add New Quote</label>
        <textarea
          class="form-control"
          cols="30"
          rows="5"
          v-model="quote"
        ></textarea>
        <button class="btn btn-primary mt-4" @click.prevent="addQuote">
          <span>Add Quote</span> 
        </button>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "NewQuote",
  data() {
    return {
      quote: "",
    };
  },

  methods: {
    addQuote() {
      this.$emit("quoteAdded", this.quote);
      this.quote = "";
    },
  },
};
</script>

<style>
.addQuote {
  padding: 20px;
}
</style>