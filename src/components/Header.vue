<template>
  <div class="row p-4">
    <div class="col-12 col-md-10">
      <h3>Quotes Addede</h3>
      <div class="progress" style="height: 30px">
        <div
          class="progress-bar bg-success"
        
          :style="{ width: (quoteCount / maxQuotes) * 100 + '%',height:30+'px' }"
        >
          {{ quoteCount }}  / {{ maxQuotes }}
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: ["quoteCount", "maxQuotes"],
};
</script>

<style>
</style>