<template>
  <VCard class="mx-5 my-2 pa-3">
    <VRow>
      <VCol v-for="n in 200" cols="1" sm="3" md="2" lg="1">
        <VCard
          @click="
            copyUrl(
              `https://picsum.photos/500/300?image=${n * 5 + 10}${
                p.isWithColor ? '' : '&grayscale'
              }`
            )
          "
        >
          <VImg
            :src="`https://picsum.photos/500/300?image=${n * 5 + 10}${
              p.isWithColor ? '' : '&grayscale'
            }`"
            :lazy-src="`https://picsum.photos/10/6?image=${n * 5 + 10}${
              p.isWithColor ? '' : '&grayscale'
            }`"
            aspect-ratio="1"
            cover
          >
            <template v-slot:placeholder>
              <VRow class="fill-height ma-0" align="center" justify="center">
                <VProgressCircular
                  indeterminate
                  color="grey-lighten-5"
                ></VProgressCircular>
              </VRow>
            </template>
          </VImg>
        </VCard>
      </VCol>
    </VRow>
  </VCard>
</template>

<script setup>
import { defineProps } from "vue";

const p = defineProps({
  isWithColor: {
    type: Boolean,
    default: true,
  },
});

const copyUrl = async (url) => {
  await navigator.clipboard.writeText(url);
};
</script>
