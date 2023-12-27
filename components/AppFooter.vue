<template>
  <div class="flex flex-row justify-between p-4">
      <p>
        &copy;{{ year }} - HP Dominic v. Grumbkow
      </p>
      <nav>
          <ul class="flex flex-row gap-6">
              <li>
                  <NuxtLink to="/legal-notice">Impressum</NuxtLink>
              </li>
              <li>
                  <NuxtLink to="/privacy-policy">Datenschutzerklärung</NuxtLink>
              </li>
          </ul>
      </nav>
  </div>
</template>

<script setup lang="ts">
  const year = ref(new Date().getFullYear())
</script>

<style scoped>

</style>