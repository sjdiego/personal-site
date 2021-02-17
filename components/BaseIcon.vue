<template>
  <div>
    <component
      :is="iconComponent"
      role="img"
      class="inline-block fill-current"
      style="height: 1em; width: 1em"
    />
  </div>
</template>

<script>
const icons = {
  download: require('./icons/DownloadIcon.vue').default,
  linkedin: require('./icons/LinkedinIcon.vue').default,
  github: require('./icons/GithubIcon.vue').default,
}

export default {
  props: {
    name: {
      type: String,
      required: true,
      validator(value) {
        return Object.prototype.hasOwnProperty.call(icons, value)
      },
    },
  },

  computed: {
    iconComponent() {
      return icons[this.name]
    },
  },
}
</script>
