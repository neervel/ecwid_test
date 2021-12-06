<template>
  <div class="item">
    {{ width }}
  </div>
</template>

<script>
export default {
  props: {
    width: Number,
    height: Number,
    url: String,
  },
};
</script>

<style lang="scss" scoped>
.item {
  display: block;
}
</style>
