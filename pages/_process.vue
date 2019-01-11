<template>
  <div class="content">
    <app-header/>

    <section class="mt-5 bg-whiteback">
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

    <section class=" p-8 bg-grey-lightest  bg-cover bg-greyligter bg-no-repeat bg-center">
          <div class="container mt-20 relative">
            <div class="text-biggest absolute pin-l ml-6 -mt-32 z-auto"> 1 </div>
            <div class="l:flex mb-4 p-5 z-10 relative">
               <div class="l:w-2/3 bg-white p-5 z-50">
                 <h1 class="leading-tight mt-2 mb-4 text-lg font-bold ">{{ home.process.pro1.header  }}</h1>
                 <p class="leading-normal ma-0 f4">{{ home.process.pro1.paragraph }}</p>
               </div>

               <div class="l:w-1/3 bg-cover bg-no-repeat ">
                 <img
                   class="object-cover h-full w-full"
                   :src="home.process.pro1.image">
               </div>
           </div>
         </div>

         <div class="container mt-20 relative">
           <div class="text-biggest absolute pin-r -mt-32 z-auto"> 2 </div>
           <div class="l:flex mb-4 p-5 z-10 relative">
              <div class="l:w-1/3 bg-cover bg-no-repeat  bg-whiteback">
                <img
                  class="object-cover h-full w-full"
                  :src="home.process.pro2.image">
              </div>
              <div class="l:w-2/3 bg-white p-5 z-50">
                 <h1 class="leading-tight mt-2 mb-4 text-lg font-bold ">{{ home.process.pro2.header }}</h1>
                 <p class="leading-normal ma-0 f4">{{ home.process.pro2.paragraph}}</p>
              </div>
            </div>
          </div>

          <div class="container mt-20 relative">
            <div class="text-biggest absolute pin-l ml-6 -mt-32 z-auto"> 3 </div>
            <div class="l:flex mb-4 p-5 z-10 relative">
               <div class="l:w-2/3 bg-white p-5 z-50">
                  <h1 class="leading-tight mt-2 mb-4 text-lg font-bold ">{{ home.process.pro3.header }}</h1>
                  <p class="leading-normal ma-0 f4">{{ home.process.pro3.paragraph}}</p>
               </div>

               <div class="l:w-1/3 bg-cover bg-no-repeat ">
                 <img
                   class="object-cover h-full w-full"
                   :src="home.process.pro3.image">
               </div>
           </div>
         </div>

         <div class="container mt-20 relative">
           <div class="text-biggest absolute pin-r -mt-32 z-auto"> 4 </div>
           <div class="l:flex mb-4 p-5 z-10 relative">
              <div class="l:w-1/3 bg-cover bg-no-repeat  bg-whiteback">
               <img
                 class="object-cover h-full w-full"
                 :src="home.process.pro4.image">
              </div>
              <div class=" l:w-2/3 bg-white p-5 z-50 relative">
                 <h1 class="leading-tight mt-2 mb-4 text-lg font-bold ">{{ home.process.pro4.header }}</h1>
                 <p class="leading-normal ma-0 f4">{{ home.process.pro4.paragraph}}</p>
              </div>
            </div>
          </div>
     </section>


     <section class="py-10 bg-whiteback">
       <h1 class="text-center text-4xl mb-12">{{ home.clients.title }}</h1>
       <div class=" flex justify-around items-center flex-wrap mx-32">
         <img
           v-for="(org, index) in home.clients.organisation"
           :key="index"
           :name=" '' + index "
           class="p-4 max-w-md w-64 "
           :src="org.image"
           :alt="org.name">
       </div>
     </section>

    <section class="py-10 bg-gradient-b-grey-lighter-white">
      <div class="max-w-md m-auto text-center">
        <h1 class="mt-0 mb-5 font-bold text-4xl leading-tight">{{ home.contactUs.title }}</h1>
        <p class="leading-normal pb-8">{{ home.contactUs.paragraph }}</p>
      </div>
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
