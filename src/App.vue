<template>
  <div class="container-fluid">
    <app-header :maxQuotes="maxQuotes" :quoteCount="quotes.length"></app-header>
    <new-quote @quoteAdded="pushQuote($event)"></new-quote>
    <quote-grid
      @quoteDeleted="removeQuote($event)"
      :quotes="quotes"
    ></quote-grid>
  </div>
</template>

<script>
import QuoteGrid from "./components/QuoteGrid.vue";
import NewQuote from "./components/NewQuote.vue";
import Header from "./components/Header.vue";
export default {
  name: "App",
  data() {
    return {
      maxQuotes: 12,
      quotes: [
        "Do one thing every day that scares you",
        "All progress takes place outside the comfort zone",
        "The way to get started is to quit talking and begin doing",
        "The way to get started is to quit talking and begin doing",
      ],
    };
  },
  methods: {
    pushQuote(quote) {
      if (this.quotes.length >= this.maxQuotes && quote.length>0) {
        alert("Please Delete Quote First !");
        return;
      }
      else if(quote.length>0){
        this.quotes.push(quote);
      }
      
    },
    removeQuote(index) {
      this.quotes.splice(index, 1);
    },
  },
  components: {
    QuoteGrid: QuoteGrid,
    newQuote: NewQuote,
    appHeader: Header,
  },
};
</script>

