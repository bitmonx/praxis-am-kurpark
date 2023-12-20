<template>
  <div class="flex justify-center">
      <div class="group feature shadow-md hover:shadow-2xl"
           :class="{'border-ci-purple shadow-ci-purple': feature.group === 1, 'border-ci-orange shadow-ci-orange': feature.group === 2}"
      >
          <NuxtImg :src="imgPath" class="opacity-30 group-hover:opacity-100" id="feature-image"></NuxtImg>
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