<template>
  <div class="col-sm-6 col-md-4 col-lg-3">
    <div class="quote">
      <slot></slot>
    </div>
  </div>
</template>

<script>
export default {
  name: "Quote",
  methods: {
    deleteQuote() {
      // emit custom event
      this.$emit("quoteDeleted", this);
    },
  },
};
</script>

<style>
.quote {
  margin: 20px;
  padding: 30px 20px;
  border: 1px solid #ddd;
  box-shadow: 1px 1px 2px #ccc;
  font-family: 'Caveat', cursive;
  font-size: 1.7rem;
  text-align: center;
  color: #6e6e6e;
}

</style>