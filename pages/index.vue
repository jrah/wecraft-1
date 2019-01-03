<template>
  <div class="content">
    <app-header/>

    <section class="mt-5 py-10 bg-whiteback text-blackback">
      <h1 class="text-center text-4xl mb-12">{{ home.clients.title }}</h1>
      <ul class=" flex list-reset ns:justify-left flex-wrap justify-center">
        <li
          v-for="(org, index) in home.clients.organisation"
          :key="index"
          class="w-24 mx-16 my-12 text-center">
          <a :href="org.href">
            <img
              :src="org.image"
              :alt="org.name"
              class="mb-5">
          </a>
        </li>
      </ul>
    </section>

    <section class="text-blackback py-10 bg-whiteback">
      <div class="text-center">
        <h1 class="mb-12 font-bold text-4xl leading-tight">{{ home.options.title }}</h1>
      </div>
      <div class="container l:flex justify-between">
        <div class="bg-whiteback bg-no-repeat p-10  m-5  l:w-1/2 border-grey-lighter border-solid border-2 rounded-sm shadow">
          <img
            :src="require('~/assets/images/'+ home.options.image+'.svg')">
        </div>
        <div class=" text-right mb-5 bg-whiteback p-10 m-5  l:w-1/2 border-grey-lighter border-solid border-2 rounded-sm shadow">
          <div class= "text-left">
            <h2
              v-if="home.options"
              class="mt-0 f1 my-2 font-bold text-2xl leading-tight">{{ home.options.project.heading }}</h2>
            <p
              v-if="home.options"
              class="m-0 my-5 leading-normal">{{ home.options.project.paragraph }}</p>
          </div>
          <a
            :href="home.options.project.href"
            class="inline-flex no-underline mt-5 bg-whiteback hover:bg-navy text-navy-dark font-semibold hover:text-white py-2 px-6 border border-navy hover:border-transparent rounded mb-2 border-white">{{ home.options.project.button }}</a>
        </div>
      </div>
    </section>

    <section>
      <div class="text-blackback container py-10 text-navy">
        <h1 class="text-center mb-12 text-4xl">{{ home.features.title }}</h1>
        <div class="m:flex l:flex justify-around">

          <div
            v-for="(block, index) in home.features.block"
            :key="index"
            :name=" '' + index "
            class="text-center ns:w-1/4">
            <div class="w-24 m-auto">
              <img
                :src="require('~/assets/images/'+ block.icon+'.svg')"
                alt="block.icon"
              >
            </div>
            <h2 class="leading-normal text-lg mt-1 mb-1">{{ block.heading }}</h2>
            <p class="leading-normal mt-0 mb-5">{{ block.paragraph }}</p>
          </div>

        </div>
      </div>
    </section>

    <section class="text-blackback py-10 bg-whiteback">
      <div class="text-center">
        <h1 class="mb-12 font-bold text-4xl leading-tight">{{ home.option.title }}</h1>
      </div>
      <div class="container l:flex justify-between">
        <div class=" text-right mb-5 bg-whiteback p-10 m-5  l:w-1/2 border-grey-lighter border-solid border-2 rounded-sm shadow">
          <div class= "text-left">
            <h1
              v-if="home.option"
              class="mt-0 f1 my-2 font-bold text-2xl leading-tight">{{ home.option.project.heading }}</h1>
            <p
              v-if="home.option"
              class=" m-0 my-5 leading-normal">{{ home.option.project.paragraph }}</p>
          </div>
          <a
            :href="home.option.project.href"
            class="inline-flex no-underline mt-5 bg-whiteback hover:bg-navy text-navy-dark font-semibold hover:text-white py-2 px-6 border border-navy hover:border-transparent rounded mb-2 border-white">{{ home.option.project.button }}</a>

        </div>
        <div class=" bg-whiteback bg-no-repeat p-10  m-5  l:w-1/2 border-grey-lighter border-solid border-2 rounded-sm shadow">
          <img
            :src="require('~/assets/images/'+ home.option.image+'.svg')">
        </div>
      </div>
    </section>

    <section class="py-12 container text-blackback">
      <h1 class="text-center text-4xl mb-12">Testimonials</h1>

      <no-ssr placeholder="Loading...">
        <carousel
          :auto-play="true"
          :pagination-active-color="'#25324e'"
          :navigation-click-target-size="20"
          :per-page="1">

          <slide
            v-for="(testimonial, index) in home.testimonial"
            :key="index"
            class="p-3">
            <figure class="text-center">
              <blockquote class="italic font-normal text-2xl mb-3 text-grey">
                {{ testimonial.quote }}
                <figcaption class="uppercase"> <cite class="author font-bold text-sm roman">- {{ testimonial.author }}</cite></figcaption>
            </blockquote></figure>
          </slide>
        </carousel>
      </no-ssr>
    </section>

    <section class="bg-whiteback text-blackback">
      <div class="container pt-12">
        <div class="max-w-md m-auto text-center">
          <h1 class="mt-0 mb-5 font-bold text-4xl leading-tight">{{ home.contactUs.title }}</h1>
          <p class="leading-normal pb-8">{{ home.contactUs.paragraph }}</p>
        </div>
      </div>
    </section>

    <section class=" bg-whiteback bg-no-repeat">
      <div class="container l:flex justify-center">
        <div class=" bg-white p-10 m-5 mt-0 l:w-2/3 border-grey-lighter border-solid border-2 rounded-sm shadow">
          <appForm/>
        </div>
        <div class="bg-whiteback p-10  m-5 mt-0 l:w-1/3 border-grey-lighter border-solid border-2 rounded-sm shadow">
          <h2 class="leading-tight mt-2 mb-4 text-lg font-bold text-navy">{{home.contactUs.text1.header}}</h2>
          <p class="leading-normal ma-0 mb-4 f4 text-sm">{{home.contactUs.text1.paragraph}}</p>
          <h2 class="leading-tight mt-2 mb-4 text-lg font-bold text-navy">{{home.contactUs.text2.header}}</h2>
          <p class="leading-normal ma-0 f4 mb-4  text-sm">{{home.contactUs.text2.paragraph}}</p>
          <h2 class="leading-tight mt-2 mb-4 text-lg font-bold text-navy">{{home.contactUs.text3.header}}</h2>
          <p class="leading-normal ma-0 f4 text-sm">{{home.contactUs.text3.paragraph}}</p>
        </div>
      </div>

    </section>

  </div>
</template>

<script>
import home from '~/content/home.json'
import appHeader from '~/components/Header.vue'
import splash from '~/components/Splash.vue'
import appForm from '~/components/Form.vue'

export default {
  components: {
    appHeader,
    splash,
    appForm
  },
  data() {
    return {
      home
    }
  }
}
</script>

<style scoped lang="scss">
.pin-container {
  position: absolute;
  &-r {
    right: 4rem;
  }
}
</style>
