<template>
  <div class="row">
    <div class="col-xs-12">
      <h2>Quotes added</h2>
      <div class="progress">
        <div class="progress-bar" role="progressbar"
          :style="{ width: (quotesLength/this.maxQuotes) * 100 + '%' }">
            <p>{{ quotesLength }} / {{ this.maxQuotes }}</p>
          </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'StatusBar',
  props: {
    quotesLength: Number,
    maxQuotes: Number,
  },
};
</script>

<style scoped lang="less">
  .progress {
    width: 100%;
    background-color: #ccc;
    height: 30px;
    border-radius: 5px;
    p {
      text-align: center;
      margin-bottom: 0px;
      color: white;
      line-height: 30px;
    }
  }
</style>
