<template>
  <v-app>
    <SideBar @selectOption="onSelectOption"/>
    <v-main>
      <ImageGallery :isColor="isColor" />
    </v-main>
  </v-app>
</template>

<script setup>
  import SideBar from "@/components/SideBar.vue"
  import ImageGallery from "@/components/ImageGallery.vue"
  import { ref } from 'vue'

  const isColor = ref(true)
  const onSelectOption = (color) => {
    isColor.value = color
  }
</script>