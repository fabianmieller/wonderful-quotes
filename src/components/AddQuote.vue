<template>
    <div class="row addQuote">
      <div class="col-xs-12 col-sm-8 col-sm-offset-2">
        <h2>Quote</h2>
        <div class="form-group" v-bind:class="{ 'has-error': error }">
          <textarea class="form-control" v-model="quote"></textarea>
          <button class="btn btn-primary" @click="addQuote">Add Quote</button>
        </div>
      </div>
    </div>
</template>

<script>
export default {
  name: 'AddQuote',
  props: {
    quotesLength: Number,
    maxQuotes: Number,
  },
  data() {
    return {
      quote: '',
      error: false,
    };
  },
  methods: {
    addQuote() {
      if (this.quote === '') {
        this.error = true;
        return;
      }

      this.error = false;

      if (this.quotesLength < this.maxQuotes) {
        console.log('Added quote');
        this.$emit('added-quote', this.quote);
        this.quote = '';
      } else {
        console.log(`You can only save ${this.maxQuotes} quotes!`);
      }
    },
  },
};
</script>

<style lang="less" scoped>
  .addQuote {

    button {
      margin: 20px auto;
      display: block;
    }
  }
</style>
