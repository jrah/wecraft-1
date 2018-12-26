<template>
  <a
    href="/"
    class="no-underline flex items-center text-grey-darkest">
    <div>

    </div>
    <img
      :src="require(`~/assets/images/${componentName}.${componentType}`)"
      class="w-24 text-white"
      alt="Logo">
    <span class="ml-4 text-3xl font-black hidden">{{componentText}}</span>
  </a>
</template>


<script>
export default {
  props: {
    componentName: {
      type: String,
      required: true
    },
    componentText: {
      type: String,
      required: true
    },
    componentType: {
      type: String,
      required: false,
      default: 'svg'
    }
  }
}
</script>
