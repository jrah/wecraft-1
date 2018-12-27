<template>
  <div class="content">
    <app-header/>

    <section class="py-10 bg-lightest">
      <div class="container">
        <h1 class="text-center text-4xl mb-12">{{ home.clients.title }}</h1>
        <ul class="container flex list-reset ns:justify-left flex-wrap items-center">
          <li
            v-for="(org, index) in home.clients.organisation"
            :key="index"
            class="w-24 mx-10 my-12 text-center">
            <a :href="org.href">
              <img
                :src="org.image"
                :alt="org.name"
                class="mb-5">
              <a class="no-underline text-grey-darker mt-1 leading-tight text-sm">{{ org.name }}</a>
            </a>
          </li>
        </ul>
      </div>
    </section>

    <section class="bg-grey-lightest text-navy">
      <div class="container pt-12 bg-lightest text-navy">
        <div class="max-w-md m-auto text-center">
          <h1 class="mt-0 mb-0 font-bold text-4xl leading-tight">{{ home.works.title }}</h1>
        </div>
      </div>
    </section>

    <section class="py-10 bg-grey-lightest">
      <div class="container l:flex justify-between">
        <div
        class=" bg-white bg-no-repeat p-10  m-5  l:w-1/2 border-grey-lighter border-solid border-2 rounded-sm shadow">
          <img
            :src="require('~/assets/images/projectimg.svg')">
        </div>
        <div class=" text-right mb-5 bg-white p-10 m-5  l:w-1/2 border-grey-lighter border-solid border-2 rounded-sm shadow">
          <div class= "text-left">
            <h1
              v-if="home.works"
              class="mt-0 f1 my-2 font-bold text-2xl leading-tight">{{ home.works.heading }}</h1>
            <p
              v-if="home.intro"
              class="m-0 my-5 leading-normal">{{ home.works.paragraph }}</p>
          </div>
          <a
            :href="home.icon_splash.href"
            class="inline-flex no-underline mt-5 bg-white hover:bg-navy text-navy-dark font-semibold hover:text-white py-2 px-6 border border-navy hover:border-transparent rounded mb-2 border-white">{{ home.works.button }}</a>

        </div>
      </div>
    </section>

    <section>
      <div class="container py-10 text-navy">
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
            <h2 class="leading-tight text-lg mt-1 mb-1">{{ block.heading }}</h2>
            <p class="leading-normal mt-0 mb-6">{{ block.paragraph }}</p>
          </div>

        </div>
      </div>
    </section>

    <section class="bg-grey-lighter text-navy">
      <div class="container pt-12 bg-lightest text-navy">
        <div class="max-w-md m-auto text-center">
          <h1 class="mt-0 mb-0 font-bold text-4xl leading-tight">{{ home.works.title }}</h1>
        </div>
      </div>
    </section>

    <section class="py-10 bg-grey-lighter">
      <div class="container l:flex justify-between">
        <div class=" text-right mb-5 bg-white p-10 m-5  l:w-1/2 border-grey-lighter border-solid border-2 rounded-sm shadow">
          <div class= "text-left">
            <h1
              v-if="home.works"
              class="mt-0 f1 my-2 font-bold text-2xl leading-tight">{{ home.works.heading }}</h1>
            <p
              v-if="home.intro"
              class="m-0 my-5 leading-normal">{{ home.works.paragraph }}</p>
          </div>
          <a
            :href="home.icon_splash.href"
            class="inline-flex no-underline mt-5 bg-white hover:bg-navy text-navy-dark font-semibold hover:text-white py-2 px-6 border border-navy hover:border-transparent rounded mb-2 border-white">{{ home.works.button }}</a>

        </div>
        <div class=" bg-white bg-no-repeat p-10  m-5  l:w-1/2 border-grey-lighter border-solid border-2 rounded-sm shadow">
          <img
            :src="require('~/assets/images/projectimg.svg')" >
        </div>
      </div>
    </section>

    <section class="py-12 container">
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
              <blockquote class="italic font-normal text-2xl mb-3 text-grey-darker">
                {{ testimonial.quote }}
                <figcaption class="uppercase"> <cite class="author font-bold text-sm roman">- {{ testimonial.author }}</cite></figcaption>
            </blockquote></figure>
          </slide>

        </carousel>
      </no-ssr>
    </section>

    <section class="bg-grey-lighter text-navy">
      <div class="container pt-12 text-navy">
        <div class="max-w-md m-auto text-center">
          <h1 class="mt-0 mb-5 font-bold text-4xl leading-tight">{{ home.contact.title }}</h1>
          <p class="leading-normal pb-8">{{ home.splash.text }}</p>
        </div>
      </div>
    </section>

    <section class=" bg-gradient-b-grey-lighter-white bg-no-repeat text-navy">
      <div class="container l:flex justify-center">
        <div class=" bg-white p-10 m-5 mt-0 l:w-2/3 border-grey-lighter border-solid border-2 rounded-sm shadow">
          <appForm/>
        </div>
        <div class=" bg-white p-10  m-5 mt-0 l:w-1/3 border-grey-lighter border-solid border-2 rounded-sm shadow">
          <h2 class="leading-tight mt-2 mb-4 text-lg font-bold text-navy">Corporate Office</h2>
          <p class="leading-normal ma-0 mb-4 f4 text-sm">8668 Concord Center Dr.Englewood, CO 80112</p>
          <h2 class="leading-tight mt-2 mb-4 text-lg font-bold text-navy">Direct Contact</h2>
          <p class="leading-normal ma-0 f4 mb-4  text-sm">Phone: 720.974.787 <br/> Toll Free: 1.877.929.7878 <br/> Email: info@choicescreening.com</p>
          <h2 class="leading-tight mt-2 mb-4 text-lg font-bold text-navy">Departments</h2>
          <p class="leading-normal ma-0 f4 text-sm">customerservice@choicescreening.com<br/>sales@choicescreening.com<br/> disputes@choicescreening.com<br/> compliance@choicescreening.com</p>
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
