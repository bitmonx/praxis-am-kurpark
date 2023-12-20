<template>
    <div class="grid lg:grid-cols-4 md:grid-cols-2 gap-10" id="features">
        <SectionsSingleFeature v-for="feature in features" :key="feature.id" :feature="feature" />
    </div>
</template>

<script setup lang="ts">
  const features = useFeature()
</script>

<style scoped>

</style>