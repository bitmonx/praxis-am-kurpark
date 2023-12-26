<template>
  <Transition>
    <div
        v-show="modalActive"
        class="modal-background"
    >
      <Transition>
        <div
            v-if="modalActive"
            class="modal-content"
        >
          <FontAwesomeIcon
              icon="fa-solid fa-xmark"
              class="absolute right-0 top-0 m-4 cursor-pointer text-lg"
              @click="$emit('close-modal')"
          />
          <div class="grid grid-cols-12 gap-x-6 p-8">
            <div class="col-span-4">
              <NuxtImg
                  v-show="feature !== null"
                  :src="imgPath"
                  class="rounded-lg shadow-lg"
              ></NuxtImg>
            </div>
            <div class="col-span-8 flex flex-col justify-evenly" id="modal-body">
              <h2 class="uppercase text-xl">
                {{ feature.title }}
              </h2>
              <p class="text-sm">
                {{ feature.description }}
              </p>
            </div>
          </div>
        </div>
      </Transition>
    </div>
  </Transition>
</template>

<script setup lang="ts">
  import type {Feature} from "@/types/Feature";
  import {FontAwesomeIcon} from "@fortawesome/vue-fontawesome";

  const props = defineProps<{
    feature: Feature|null,
    modalActive: Boolean,
  }>()

  const imgPath = computed(() => {
    if (props.feature !== null) {
      return '/img/' + props.feature.image
    }
  })
</script>

<style lang="css" scoped>
.v-enter-active,
.v-leave-active {
  @apply transition-all duration-300 ease-in-out;
}

.v-enter-from,
.v-leave-to {
  @apply opacity-0;
}
</style>