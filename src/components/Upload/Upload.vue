<template>
  <div class="upload">
    <form action="#">
      <input type="file" id="fileUpload" placeholder="Загрузите файл" />
      <input type="button" value="Load" @click="loadFile" />
    </form>
  </div>
</template>

<script>
export default {
  name: "Upload",
  data() {
    return {
      images: [],
    };
  },
  methods: {
    loadFile() {
      const input = document.getElementById("fileUpload");
      if (input.files.length > 0) {
        const file = input.files[0];
        let fr = new FileReader();
        fr.onload = this.receivedText;
        fr.readAsText(file);
      } else {
        alert("Файл не выбран!");
      }
    },
    receivedText(e) {
      const input = document.getElementById("fileUpload");
      const lines = e.target.result;
      let newArr = {};
      try {
        newArr = JSON.parse(lines);
        const key = Object.keys(newArr)[0];
        this.images = newArr[key];
        this.$emit("imagesUploaded", this.images);
        input.value = "";
        alert("Данные сохранены успешно!");
      } catch {
        alert("Неправильный формат файла!");
        input.value = "";
      }
    },
  },
};
</script>

<style lang="scss" scoped></style>
