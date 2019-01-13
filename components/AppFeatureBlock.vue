<template lang="html">

  <section :class="componentBackgroundColor" class="bg-grey-lightest">
    <div class="container py-10">
      <h1 class="mb-16 text-4xl text-center">{{ componentTitle }}</h1>
      <div class="flex flex-wrap justify-between">
        <div
         v-for="(block, index) in componentLoop"
         :key="index"
         :name=" '' + index "
         class="w-full m:w-1/2 l:w-1/4 px-4">
         <div class="max-w-xs m-auto">
           <img
             :src="block.icon"
             :alt="block.icon">
         </div>
         <h2 class="leading-normal text-lg mt-1 mb-1">{{ block.heading }}</h2>
         <p class="leading-normal mt-0 mb-5">{{ block.paragraph }}</p>
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
      default: ''
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
