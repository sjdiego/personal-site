<template>
  <div
    class="m-2 bg-white text-gray-800 font-bold rounded-md shadow-md hover:shadow-lg transition duration-300"
  >
    <a
      :href="url"
      :target="external ? '_blank' : null"
      class="py-2 px-4 rounded inline-flex items-center"
    >
      <base-icon :name="icon"></base-icon>
      <p class="ml-1 text-sm">
        <slot></slot>
      </p>
    </a>
  </div>
</template>

<script>
import BaseIcon from './BaseIcon.vue'

export default {
  components: { BaseIcon },
  props: {
    icon: {
      type: String,
      default: 'download',
    },
    url: {
      type: String,
      default: '#',
    },
    external: {
      type: Boolean,
      default: false,
    },
  },
}
</script>
