<template>
  <VNavigationDrawer expand-on-hover rail>
    <VList>
      <VListItem
        prepend-avatar="https://media.licdn.com/dms/image/C4D03AQFZxkNEftgZDQ/profile-displayphoto-shrink_100_100/0/1647686816681?e=1714608000&v=beta&t=E3LcQXgy_wWvMiBg8NKtp9g3w-7WqujFVDOdhYc1TjQ"
        title="Areeb Khan"
        subtitle="ak6253160@gmailcom"
      ></VListItem>
    </VList>

    <VDivider />

    <VList density="compact" nav>
      <VListItem
        prepend-icon="mdi-image"
        title="Color Gallery"
        value="color"
        @click="selectColorOption(true)"
      />
      <VListItem
        prepend-icon="mdi-dialpad"
        title="Grayspace Gallery"
        value="grayspace"
        @click="selectColorOption(false)"
      />
    </VList>
  </VNavigationDrawer>
</template>

<script setup>
import { defineEmits } from "vue";

const emits = defineEmits(["selectColorOption"]);

const selectColorOption = (isColor) => {
  emits("selectColorOption", isColor);
};
</script>
