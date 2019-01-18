<template lang="html">

  <section
    :class="componentBackgroundColor">
    <div class="container py-10">
      <h1 class="mb-16 text-4xl text-center">{{ componentTitle }}</h1>

      <div
        v-if="componentLoop.length <= 4"
        class="flex flex-wrap justify-between">

        <div
          v-for="(block, index) in componentLoop"
          :key="index"
          :name=" '' + index "
          class="w-full m:w-1/2 l:w-1/4 px-4 text-center">

          <div class="max-w-xs m-auto">
            <img
              :src="block.icon"
              :alt="block.icon">
          </div>
          <h2 class="leading-normal text-lg mt-2 mb-3">{{ block.heading }}</h2>
          <p class="leading-normal mt-0 mb-5">{{ block.paragraph }}</p>
        </div>
      </div>
      <div
        v-else
        class="flex flex-wrap justify-between">
        <div
          v-for="(block, index) in componentLoop"
          :key="index"
          :name=" '' + index "
          class="w-full m:w-1/2 l:w-1/3">
          <h2 class="leading-normal text-lg mt-2 mb-3"><span class="mr-2 text-grey-darkest">{{ index + 1 }}</span> <span class="uppercase font-medium border-b-4 border-teal-light">{{ block.heading }}</span></h2>
          <p class="leading-normal mt-0 mb-5 ml-5">{{ block.paragraph }}</p>
        </div>
      </div>

    </div>
  </section>

</template>

<script>
export default {
  props: {
    componentTitle: {
      type: String,
      required: true
    },
    componentBackgroundColor: {
      type: String,
      required: false,
      default: ""
    },
    componentLoop: {
      type: Array,
      required: true
    }
  }
};
</script>

<style lang="css">

</style>
