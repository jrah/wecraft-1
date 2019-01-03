<template>
  <div>

    <div
    :style="{'background-image' : 'url('+home.image+')'}"
    class="bg-cover bg-center py-6 relative bg-grey-darkest">
      <div class="container py-32 relative z-10">
        <div class="m:w-3/5 l:w-2/5">
          <h1>
            <span class="text-point font-majorMonoDisplay mt-0 f1 mb-2 text-5xl leading-tight">{{ home.title }}</span><br/>
            <span class="text-whiteback mt-0 f1 mb-2 text-3xl leading-normal">{{ home.subtitle }}</span>
          </h1>
          <p
            v-if="home.intro"
            class="text-whiteback m-0 mb-12 leading-normal">{{ home.intro }}</p>
            <!-- <a
              href="#"
              class="no-underline inline-block shadow bg-navy hover:bg-navy-light focus:shadow-outline focus:outline-none text-white font-bold py-2 px-4 rounded cursor-pointer my-3">Click Here</a> -->
        </div>
        <a
          :href="home.contactEmail"
          class="no-underline inline bg-transparent hover:bg-navy text-whiteback font-bold hover:text-white py-2 px-6 border-2 border-white hover:border-transparent mb-2 border-white">{{ home.button }}</a>
      </div>
      <div
        class="overlay"
    </div>

  </div>
</template>

<script>
import home from '~/content/home.json'

export default {
  data() {
    return {
      home
    }
  }
}
</script>

<style lang="scss">
.overlay {
  position: absolute;
  @apply pin;
  z-index: 1;
  display: block;
}
</style>
