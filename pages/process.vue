<template>
  <div class="content">
    <app-header/>

    <section class="mt-5 bg-white text-navy">
      <div class="p-12 bg-lightest text-navy">
        <div class="max-w-md m-auto text-center">
          <img
            :src="require(`~/assets/images/logo0.svg`)"
            class="w-24"
            alt="Logo">
            <p class=" blockquote leading-normal p-8 m-5"> {{home.discrip }}</p>
        </div>
      </div>
    </section>

    <section class="bg-grey-lighter text-navy">
      <div class="container pt-12 bg-greyligter text-navy">
        <div class="max-w-md m-auto text-center">
          <h1 class=" mt-0 font-bold text-4xl leading-tight">{{ home.process.title }}</h1>
        </div>
      </div>
    </section>

    <section class=" p-8 bg-grey-lighter text-black bg-cover bg-greyligter bg-no-repeat bg-center">
         <div class="mt-24 container relative">
          <div class="flex mb-4">
             <img
                :src="require('~/assets/images/2052171.svg')"
                alt="block.icon"
                class="w-24 absolute -ml-20 z-auto -mt-16"
              >
              <div class="w-3/4 bg-white p-5 z-50">
                 <h1 class="leading-tight mt-2 mb-4 text-lg font-bold text-navy">{{ home.options.quiz.heading }}</h1>
                 <p class="leading-normal ma-0 f4">{{ home.options.quiz.paragraph + home.options.quiz.paragraph + home.options.quiz.paragraph +home.options.quiz.paragraph}}</p>
                 <span class="inline-block my-3 font-bold text-sm text-grey no-underline">Coming Soon</span>
              </div>
              <div
              :style="{'background-image' : 'url(/images/uploads/name1.jpg)'}"
               class="w-1/4 bg-purple-lightest bg-cover">

              </div>
          </div>
        </div>

        <div class="container mt-20 relative">
          <div class="flex mb-4">
            <img
               :src="require('~/assets/images/2052150.svg')"
               alt="block.icon"
               class="w-24 absolute pin-r -mr-5 -mt-16 z-auto"
             >
             <div
             :style="{'background-image' : 'url(/images/uploads/name2.jpg)'}"
             class="w-1/4 bg-cover bg-no-repeat p-5">
             </div>
             <div class="w-3/4 bg-white p-5 z-50">
                <h1 class="leading-tight mt-2 mb-4 text-lg font-bold text-navy">{{ home.options.quiz.heading }}</h1>
                <p class="leading-normal ma-0 f4">{{ home.options.quiz.paragraph + home.options.quiz.paragraph + home.options.quiz.paragraph +home.options.quiz.paragraph}}</p>
                <span class="inline-block my-3 font-bold text-sm text-grey no-underline">Coming Soon</span>
             </div>
           </div>
         </div>

         <div class="container mt-20 relative">
          <div class="flex mb-4">
             <img
                :src="require('~/assets/images/2052130.svg')"
                alt="block.icon"
                class="w-24 absolute pin-l -ml-5 -mt-16 z-auto"
              >
              <div class="w-3/4 bg-white p-5 z-50">
                 <h1 class="leading-tight mt-2 mb-4 text-lg font-bold text-navy">{{ home.options.quiz.heading }}</h1>
                 <p class="leading-normal ma-0 f4">{{ home.options.quiz.paragraph + home.options.quiz.paragraph + home.options.quiz.paragraph +home.options.quiz.paragraph}}</p>
                 <span class="inline-block my-3 font-bold text-sm text-grey no-underline">Coming Soon</span>
              </div>

              <div
              :style="{'background-image' : 'url(/images/uploads/name3.jpg)'}"
              class="w-1/4 bg-cover bg-no-repeat p-5">
              </div>
          </div>
        </div>

        <div class="container mt-20 relative">
          <div class="flex mb-4">
             <img
               :src="require('~/assets/images/2052105.svg')"
               alt="block.icon"
               class="w-24 absolute pin-r z-auto -mr-5 -mt-16"
             >
             <div
             :style="{'background-image' : 'url(/images/uploads/name4.jpg)'}"
             class="w-1/4 bg-cover bg-no-repeat p-5">

             </div>
             <div class="w-3/4 bg-white p-5 z-50">
                <h1 class="leading-tight mt-2 mb-4 text-lg font-bold text-navy">{{ home.options.quiz.heading }}</h1>
                <p class="leading-normal ma-0 f4">{{ home.options.quiz.paragraph + home.options.quiz.paragraph + home.options.quiz.paragraph +home.options.quiz.paragraph}}</p>
                <span class="inline-block my-3 font-bold text-sm text-grey no-underline">Coming Soon</span>
             </div>
           </div>
         </div>
    </section>

    <section class="py-10 bg-lightest">
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
            <a class="no-underline text-grey-darker mt-1 leading-tight text-sm">{{ org.name }}</a>
          </a>
        </li>
      </ul>
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
.blockquote:before {
  content: "\201C";
  font-size: 5em;
  font-family: Georgia;
  color: #bcbcbc;
  float: left;
  margin: -40px 20px 0px -50px;
}
.blockquote:after {
  content: "\201D";
  font-size: 5em;
  font-family: Georgia;
  color: #bcbcbc;
  float: right;
  margin: 0px -50px 0px 0px;
}
</style>
