<template>
  <div id="app">
    <div class="upload">
      <upload @imagesUploaded="setImages" />
    </div>
    <div class="gallery">
      <gallery :images="images" />
    </div>
  </div>
</template>

<script>
import Gallery from "./components/Gallery/Gallery.vue";
import Upload from "./components/Upload/Upload.vue";

export default {
  name: "App",
  components: {
    Gallery,
    Upload,
  },
  data() {
    return {
      images: [],
    };
  },
  methods: {
    setImages(images) {
      this.images = images;
    },
  },
};
</script>

<style></style>
