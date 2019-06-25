<template>
    <div class="col-xs-12 col-sm-3 quote-box">
        <slot></slot>
    </div>
</template>

<script>
export default {
  name: 'Quote',
};
</script>

<style lang="less" scoped>
  .quote-box {
    cursor: pointer;
    padding: 10px;
    p {
      padding: 20px;
      border-radius: 5px;
      border: 1px solid grey;
      font-family: Arizonia;
      font-size: 28px;
    }
  }
</style>
