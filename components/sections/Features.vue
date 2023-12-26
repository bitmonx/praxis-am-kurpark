<template>
    <div class="grid lg:grid-cols-4 md:grid-cols-2 gap-10" id="features">
        <SectionsSingleFeature @click="openModal(feature)" v-for="feature in features" :key="feature.id" :feature="feature" />
    </div>
  <FeatureModal
      :modal-active="modalActive"
      :feature="modalFeature"
      @close-modal="closeModal"
  ></FeatureModal>
</template>

<script setup lang="ts">
  import type {Feature} from "@/types/Feature";

  const features = useFeature()

  const modalFeature = ref<Feature|null>(null)

  const modalActive = ref(false)

  const openModal = (feature:Feature) => {
    modalFeature.value = feature
    modalActive.value = true
  }

  const closeModal = () => {
    modalFeature.value = null
    modalActive.value = false
  }
</script>

<style scoped>

</style>