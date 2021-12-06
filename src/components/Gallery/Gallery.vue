<template>
  <div class="gallery">
    <gallery-item />
  </div>
</template>

<script>
import GalleryItem from "./GalleryItem.vue";
export default {
  name: "Gallery",
  components: {
    GalleryItem,
  },
};
</script>

<style lang="scss" scoped>
.gallery {
  display: grid;
}
</style>
