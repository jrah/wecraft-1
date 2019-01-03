<template>
  <div class="content">
    <app-header/>

    <section class="mt-5 bg-whiteback text-blackback">
      <div class="p-12 bg-whiteback">
        <div class="max-w-md m-auto text-center">
          <img
            :src="require('~/assets/images/'+ home.logo +'.svg')"
            class="w-24"
            alt="Logo">
            <p class="blockquote leading-normal p-8 m-5"> {{home.discrip }}</p>
        </div>
      </div>
    </section>

    <section class=" p-8 bg-grey-lightest text-black bg-cover bg-greyligter bg-no-repeat bg-center">
          <div class="container mt-20 relative">
            <img
              :src="require('~/assets/images/'+ home.process.pro1.number +'.svg')"
               alt="block.icon"
               class="w-24 absolute pin-l -ml-0 -mt-16 z-auto"
             >
           <div class="l:flex mb-4 p-5 z-10 relative">
               <div class="l:w-2/3 bg-white p-5 z-50">
                 <h1 class="leading-tight mt-2 mb-4 text-lg font-bold text-navy">{{ home.process.pro1.header  }}</h1>
                 <p class="leading-normal ma-0 f4">{{ home.process.pro1.paragraph }}</p>
               </div>

               <div
               :style="{'background-image' : 'url('+home.process.pro1.image+')'}"
               class="l:w-1/3 bg-cover bg-no-repeat p-5">
               </div>
           </div>
         </div>

         <div class="container mt-20 relative">
           <img
              :src="require('~/assets/images/'+ home.process.pro2.number +'.svg')"
              alt="block.icon"
              class="w-24 absolute pin-r -mr-0 -mt-16 z-auto"
            >
           <div class="l:flex mb-4 p-5 z-10 relative">
              <div
              :style="{'background-image' : 'url('+home.process.pro2.image+')'}"
              class="l:w-1/3 bg-cover bg-no-repeat p-5">
              </div>
              <div class="l:w-2/3 bg-white p-5 z-50">
                 <h1 class="leading-tight mt-2 mb-4 text-lg font-bold text-navy">{{ home.process.pro2.header }}</h1>
                 <p class="leading-normal ma-0 f4">{{ home.process.pro2.paragraph}}</p>
              </div>
            </div>
          </div>

          <div class="container mt-20 relative">
            <img
              :src="require('~/assets/images/'+ home.process.pro3.number +'.svg')"
               alt="block.icon"
               class="w-24 absolute pin-l -ml-0 -mt-16 z-auto"
             >
           <div class="l:flex mb-4 p-5 z-10 relative">
               <div class="l:w-2/3 bg-white p-5 z-50">
                  <h1 class="leading-tight mt-2 mb-4 text-lg font-bold text-navy">{{ home.process.pro3.header }}</h1>
                  <p class="leading-normal ma-0 f4">{{ home.process.pro2.paragraph}}</p>
               </div>

               <div
               :style="{'background-image' : 'url('+home.process.pro3.image+')'}"
               class="l:w-1/3 bg-cover bg-no-repeat p-5">
               </div>
           </div>
         </div>

         <div class="container mt-20 relative">
           <img
             :src="require('~/assets/images/'+ home.process.pro4.number +'.svg')"
             alt="block.icon"
             class="w-24 absolute pin-r z-auto -mr-0 -mt-16"
           >
           <div class="l:flex mb-4 p-5 z-10 relative">
              <div
              :style="{'background-image' : 'url('+home.process.pro4.image+')'}"
              class="l:w-1/3 bg-cover bg-no-repeat p-5">

              </div>
              <div class=" l:w-2/3 bg-white p-5 z-50 relative">
                 <h1 class="leading-tight mt-2 mb-4 text-lg font-bold text-navy">{{ home.process.pro4.header }}</h1>
                 <p class="leading-normal ma-0 f4">{{ home.process.pro4.paragraph}}</p>
              </div>
            </div>
          </div>
     </section>


    <section class="py-10 bg-whiteback ">
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

    <section class="bg-grey-lightest text-blackback">
      <div class="container pt-12">
        <div class="max-w-md m-auto text-center">
          <h1 class="mt-0 mb-5 font-bold text-4xl leading-tight">{{ home.contactUs.title }}</h1>
          <p class="leading-normal pb-8">{{ home.contactUs.paragraph }}</p>
        </div>
      </div>
    </section>

    <section class=" bg-gradient-b-grey-lighter-white bg-no-repeat">
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
