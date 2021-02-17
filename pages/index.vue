<template>
  <div class="bg-gray-100 h-screen font-sans subpixel-antialiased">
    <div class="container mx-auto p-8 sm:p-10 md:p-20 lg:p-30 xl:p-40">
      <div class="flex flex-col m-2 my-4">
        <h1 class="text-3xl text-medium my-4">Hi!</h1>
        <p class="text-medium">
          My name is Diego Ortiz and I am a web developer from Palma de
          Mallorca, Spain 🇪🇸
        </p>
        <nuxt-content :document="intro" />
      </div>

      <div class="flex flex-row">
        <labeled-button
          :external="true"
          icon="linkedin"
          url="https://www.linkedin.com/in/drtiz"
          >Linkedin</labeled-button
        >
        <labeled-button
          :external="true"
          icon="github"
          url="https://github.com/sjdiego"
          >Github</labeled-button
        >
        <labeled-button
          :external="true"
          icon="download"
          url="mailto:diego at this domain"
          >Email</labeled-button
        >
      </div>
    </div>
  </div>
</template>

<script>
import LabeledButton from '~/components/LabeledButton.vue'

export default {
  components: { LabeledButton },

  async asyncData({ $content }) {
    const intro = await $content('intro').fetch()

    return {
      intro,
    }
  },
}
</script>

<style>
.nuxt-content p {
  font-weight: 300;
  padding-top: 1em;
  line-height: 2em;
}
</style>
