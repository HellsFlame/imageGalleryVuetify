<template>
  <VApp>
    <Sidebar @selectColorOption="onSelectOption" />
    <VMain>
      <ImageGallery :isWithColor="isWithColor" />
    </VMain>
  </VApp>
</template>

<script setup>
import Sidebar from "./components/Sidebar.vue";
import ImageGallery from "./components/ImageGallery.vue";
import { ref } from "vue";

const isWithColor = ref(true);

const onSelectOption = (isColor) => {
  isWithColor.value = isColor;
};
</script>
