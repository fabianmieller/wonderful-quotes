<template>
  <div id="app" class="container">
    <StatusBar :quotesLength=quotes.length :maxQuotes=maxQuotes />
    <AddQuote :quotesLength=quotes.length :maxQuotes=maxQuotes @added-quote="addQuote" />
    <ListQuotes :quotes=quotes @deleted-quote="deleteQuote" />
  </div>
</template>

<script>
import StatusBar from './components/StatusBar.vue';
import AddQuote from './components/AddQuote.vue';
import ListQuotes from './components/ListQuotes.vue';

export default {
  name: 'app',
  data() {
    return {
      quotes: [
        'A quote',
      ],
      maxQuotes: 7,
    };
  },
  methods: {
    addQuote(quote) {
      console.log('added');
      this.quotes.push(quote);
    },
    deleteQuote(index) {
      console.log('deleted');
      this.quotes.splice(index, 1);
    },
  },
  components: {
    StatusBar,
    AddQuote,
    ListQuotes,
  },
};
</script>

<style lang="less">
</style>
