<template>
  <div class="row list-quotes">
    <div class="col-xs-12">
      <div class="row">
        <quote
          v-for="(quote, i) in quotes"
          :key="i"
          @click.native="deleteQuote(i)">
          <p>{{quote}}</p>
        </quote>
      </div>
      <p class="bg-info">Info: Click box to delete quote</p>
    </div>
  </div>
</template>

<script>
import Quote from './Quote.vue';

export default {
  name: 'ListQuotes',
  props: {
    quotes: Array,
  },
  methods: {
    deleteQuote(index) {
      this.$emit('deleted-quote', index);
    },
  },
  components: {
    Quote,
  },
};
</script>

<style lang="less" scoped>
  .list-quotes {
    margin-top: 20px;
  }
  .bg-info {
    padding: 15px;
  }
</style>
