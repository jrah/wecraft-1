<template lang="html">
  <section class="py-10">
    <div class="text-center">
      <h1 class="mb-12 font-bold text-4xl leading-tight">{{ componentTitle }}</h1>
    </div>
    <div
      :class="'l:'+ componentFlexDirection"
      class="container flex justify-between flex-col">
      <div class="w-full l:w-1/2 flex items-center">
        <div class="px-4">
          <img
            :src="componentImage"
            :alt="componentImage +' Image'">
        </div>
      </div>
      <div class="p-10 w-full l:w-1/2 border-grey-lighter border-solid border-2 rounded-sm shadow">
        <h2
          v-if="componentSubHeading"
          class="mt-0 f1 my-2 font-bold text-2xl leading-tight">{{ componentSubHeading }}</h2>
        <p
          v-if="componentParagraph"
          class=" m-0 my-5 leading-normal">{{ componentParagraph }}</p>
        <div class="flex justify-end">
          <a
            :href="componentHref"
            class="bg-point hover:bg-point-light text-white font-bold py-2 px-4 border-b-4 border-point-dark hover:border-point rounded no-underline">Visit {{ componentTitle }}</a>
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
    componentSubHeading: {
      type: String,
      required: false,
      default: ""
    },
    componentParagraph: {
      type: String,
      required: true
    },
    componentHref: {
      type: String,
      required: true,
      default: "#"
    },
    componentImage: {
      type: String,
      required: true
    },
    componentBackgroundColor: {
      type: String,
      required: false,
      default: ""
    },
    componentFlexDirection: {
      type: String,
      required: false,
      default: "flex-row"
    }
  }
};
</script>

<style lang="css">
</style>
