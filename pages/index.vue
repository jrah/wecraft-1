<template>
  <div class="content">
    <app-header/>

    <section>
      <div class=" container py-10 text-center">
        <h1 class="text-center mb-12 text-4xl">{{ home.offers.title }}</h1>
        <div class="m:flex l:flex justify-around">

          <div
            v-for="(block, index) in home.offers.block"
            :key="index"
            :name=" '' + index "
            class="text-center ns:w-1/4">
            <div class="w-24 m-auto">
              <img
                :src="block.icon"
                alt="block.icon"
              >
            </div>
            <h2 class="leading-normal text-lg mt-1 mb-1">{{ block.heading }}</h2>
            <p class="leading-normal mt-0 mb-5">{{ block.paragraph }}</p>
          </div>

        </div>
        <a
          :href="home.offers.link"
          class="mt-5 inline-flex no-underline bg-whiteback hover:bg-point text-blackbasic font-semibold hover:text-whiteback py-2 px-6 border rounded hover:border-transparent  border-blackbasic">{{ home.offers.button }}</a>

      </div>
    </section>

    <section class="mt-5 py-10 bg-whiteback">
      <h1 class="text-center text-4xl mb-12">{{ home.clients.title }}</h1>
      <div class=" container flex justify-around items-center flex-wrap">
        <img
          v-for="(org, index) in home.clients.organisation"
          :key="index"
          :name=" '' + index "
          class="p-4 max-w-md"
          :src="org.image"
          :alt="org.name">
      </div>
    </section>

    <section class=" py-10 bg-grey-lightest">
      <div class="text-center">
        <h1 class="mb-12 font-bold text-4xl leading-tight">{{ home.options.heading }}</h1>
      </div>
      <div class="container l:flex justify-between">
        <div class=" bg-whiteback bg-no-repeat p-0 m-5 l:w-1/2 border-grey-lighter border-solid border-2 rounded-sm shadow">
            <img
              class="object-cover h-full w-full p-0"
              :src="home.options.image.icon">
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
            class="mt-5 inline-flex no-underline bg-whiteback hover:bg-point text-blackbasic font-semibold hover:text-whiteback py-2 px-6 border rounded hover:border-transparent  border-blackbasic">{{ home.options.project.button }}</a>
        </div>
      </div>
    </section>

    <section>
      <div class="container py-10">
        <h1 class="text-center mb-12 text-4xl">{{ home.features.title }}</h1>
        <div class="m:flex l:flex justify-around">

          <div
            v-for="(block, index) in home.features.block"
            :key="index"
            :name=" '' + index "
            class="text-center ns:w-1/4">
            <div class="w-24 m-auto">
              <img
                :src="block.icon"
                alt="block.icon"
              >
            </div>
            <h2 class="leading-normal text-lg mt-1 mb-1">{{ block.heading }}</h2>
            <p class="leading-normal mt-0 mb-5">{{ block.paragraph }}</p>
          </div>

        </div>
      </div>
    </section>

    <section class="py-10 bg-grey-lightest">
      <div class="text-center">
        <h1 class="mb-12 font-bold text-4xl leading-tight">{{ home.options2.heading }}</h1>
      </div>
      <div class="container l:flex justify-between">
        <div class=" text-right mb-5 bg-whiteback p-10 m-5  l:w-1/2 border-grey-lighter border-solid border-2 rounded-sm shadow">
          <div class= "text-left">
            <h1
              v-if="home.options2"
              class="mt-0 f1 my-2 font-bold text-2xl leading-tight">{{ home.options2.project.heading }}</h1>
            <p
              v-if="home.options2"
              class=" m-0 my-5 leading-normal">{{ home.options2.project.paragraph }}</p>
          </div>
          <a
            :href="home.options2.project.href"
            class="mt-5 inline-flex no-underline bg-whiteback hover:bg-point text-blackbasic font-semibold hover:text-whiteback py-2 px-6 border rounded hover:border-transparent  border-blackbasic">{{ home.options2.project.button }}</a>

        </div>
        <div class=" bg-whiteback bg-no-repeat p-0 m-5 l:w-1/2 border-grey-lighter border-solid border-2 rounded-sm shadow">
            <img
              class="object-cover h-full w-full p-0"
              :src="home.options2.image.icon">
        </div>
      </div>
    </section>
<!--
    <section class="py-12 container ">
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
              <blockquote class="italic font-normal text-2xl mb-3 text-blackbasic">
                {{ testimonial.quote }}
                <figcaption class="uppercase"> <cite class="author font-bold text-sm roman">- {{ testimonial.author }}</cite></figcaption>
            </blockquote></figure>
          </slide>
        </carousel>
      </no-ssr>
    </section>
!-->
    <section class="bg-grey-lightest">
      <div class="container pt-12">
        <div class="max-w-md m-auto text-center">
          <h1 class="mt-0 mb-5 font-bold text-4xl leading-tight">{{ home.contactUs.title }}</h1>
          <p class="leading-normal pb-8">{{ home.contactUs.paragraph }}</p>
        </div>
      </div>
    </section>

    <section class=" bg-gradient-b-grey-lighter-white">
      <div class="container l:flex justify-center">
        <div class=" bg-white p-10 m-5 mt-0 l:w-2/3 border-grey-lighter border-solid border-2 rounded-sm shadow">
          <appForm/>
        </div>
        <div class="bg-whiteback p-10  m-5 mt-0 l:w-1/3 border-grey-lighter border-solid border-2 rounded-sm shadow">
          <h2 class="leading-tight mt-2 mb-4 text-lg font-bold ">{{home.contactUs.text1.header}}</h2>
          <p class="leading-normal ma-0 mb-4 f4 text-sm">{{home.contactUs.text1.paragraph}}</p>
          <h2 class="leading-tight mt-2 mb-4 text-lg font-bold">{{home.contactUs.text2.header}}</h2>
          <p class="leading-normal ma-0 f4 mb-4  text-sm">{{home.contactUs.text2.paragraph}}</p>
          <h2 class="leading-tight mt-2 mb-4 text-lg font-bold">{{home.contactUs.text3.header}}</h2>
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
