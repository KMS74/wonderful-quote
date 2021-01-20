<template>
  <div class="row">
    <app-quote v-for="(quote,index) in quotes" :key="quote">
      <p>"{{ quote }}"</p>
      
      <button @click="deleteQuote(index)" class="btn btn-danger"><i class="icon fa fa-trash" aria-hidden="false"></i></button>

    </app-quote>
  </div>
</template>

<script>
import Quote from "./Quote.vue";
export default {
  name: "QuoteGrid",
  props: {
    quotes: Array,
  },
  components: {
    appQuote: Quote,
  },
  methods: {
    deleteQuote(index) {
      this.$emit("quoteDeleted", index);
    },
  },
};
</script>

