<template>
  <div
    :style="{'background-image' : 'url('+home.image+')'}"
    class="bg-cover bg-center ns:h-screen relative bg-grey-darkest">
    <div class="container h-full relative ns:flex flex-col justify-center pt-32 pb-24 ns:h-100 z-10">
      <div class="m:w-3/5 l:w-2/5">
        <div v-if="home.subtitle">
          <h1>
            <span class="text-point font-majorMonoDisplay mt-0 f1 mb-2 text-5xl l:text-headline leading-tight">{{ home.title }}</span>
            <span
              v-if="home.subtitle"
              class="text-whiteback mt-0 f1 mb-2 text-3xl leading-normal">{{ home.subtitle }}</span>
          </h1>
        </div>
        <div else>
          <h1 class="text-point font-majorMonoDisplay mt-0 f1 mb-2 text-5xl l:text-headline leading-tight">
            {{ home.title }}
          </h1>
        </div>
        <p
          v-if="home.intro"
          class="text-whiteback m-0 mb-6 leading-normal">{{ home.intro }}</p>
        <a
          :href="home.contactEmail"
          class="no-underline inline bg-transparent hover:bg-point text-whiteback font-bold hover:text-whiteback py-2 px-6 border-2 border-whiteback hover:border-transparent">{{ home.button }}</a>
      </div>
    </div>
    <div class="overlay"/>
  </div>

</template>

<script>
import home from "~/content/home.json";

export default {
  data() {
    return {
      home
    };
  }
};
</script>

<style lang="scss">
.overlay {
  position: absolute;
  @apply pin;
  z-index: 1;
  display: block;
}
</style>
