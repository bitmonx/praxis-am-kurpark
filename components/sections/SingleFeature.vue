<template>
  <div class="flex justify-center items-center w-72">
      <div class="group feature shadow-lg hover:shadow-2xl">
          <NuxtImg preload :src="imgPath" class="opacity-40 group-hover:opacity-100" id="feature-image"></NuxtImg>
          <div class="absolute uppercase text-xl text-center font-bold m-5 pointer-events-none group-hover:opacity-0 transition-all duration-500 ">
              {{feature.title}}
          </div>
      </div>
  </div>
</template>

<script setup lang="ts">
  import type { Feature } from "@/types/Feature";

  const props = defineProps<{
      feature: Feature,
  }>()

  const imgPath = computed(() => {
      return '/img/' + props.feature.image
  })

</script>

<style scoped>
#feature-image {
    transition: opacity 500ms ease-in-out;
}
</style>