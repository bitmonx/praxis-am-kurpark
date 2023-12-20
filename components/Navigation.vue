<template>
  <nav class="justify-end px-5 hidden lg:flex">
      <ul class="flex gap-4 text-2xl">
          <li>
              <NuxtLink :to="{path: '/', hash: '#welcome'}"><span>Willkommen</span></NuxtLink>
          </li>
          <li>
              <NuxtLink :to="{path: '/', hash: '#intro'}"><span>Über mich</span></NuxtLink>
          </li>
          <li>
              <NuxtLink :to="{path: '/', hash: '#features'}"><span>Schwerpunkt</span></NuxtLink>
          </li>
          <li>
              <NuxtLink :to="{path: '/', hash: '#contact'}"><span>Kontakt</span></NuxtLink>
          </li>
      </ul>
  </nav>
</template>

<script setup lang="ts">

</script>

<style scoped>
</style>