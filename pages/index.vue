<template>
  <div class="content">
    <app-header/>

    <section class="py-10 text-center bg-grey-lightest">
      <h1 class="mb-16 text-4xl">{{ home.offers.title }}</h1>
      <div class="container flex flex-wrap justify-between">
         <div
          v-for="(block, index) in home.offers.block"
          :key="index"
          :name=" '' + index "
          class="w-full m:w-1/2 l:w-1/4 px-4">
          <div class="max-w-xs m-auto">
            <img
              :src="block.icon"
              :alt="block.icon">
          </div>
          <h2 class="leading-normal text-lg mt-1 mb-1">{{ block.heading }}</h2>
          <p class="leading-normal mt-0 mb-5">{{ block.paragraph }}</p>
        </div>
      </div>
    </section>



    <section class="py-10 bg-grey-lightest">
      <h1 class="text-center mb-16 text-4xl">{{ home.features.title }}</h1>
      <div class="container  m:flex l:flex justify-around">
        <div
          v-for="(block, index) in home.features.block"
          :key="index"
          :name=" '' + index "
          class="text-center ns:w-1/4">
          <div class="w-48 m-auto">
            <img
              :src="block.icon"
              alt="block.icon">
          </div>
          <h2 class="leading-normal text-lg mt-1 mb-1">{{ block.heading }}</h2>
          <p class="leading-normal mt-0 ">{{ block.paragraph }}</p>
        </div>
      </div>
    </section>


    <app-case-study
      :component-sub-heading="home.caseStudyTwo.subheading"
      :component-href="home.caseStudyTwo.href"
      :component-title="home.caseStudyTwo.heading"
      :component-image="home.caseStudyTwo.image"
      :component-paragraph="home.caseStudyTwo.paragraph"/>

    <app-case-study
      :component-flex-direction="'flex-row-reverse'"
      :component-sub-heading="home.caseStudyOne.subheading"
      :component-href="home.caseStudyOne.href"
      :component-title="home.caseStudyOne.heading"
      :component-image="home.caseStudyOne.image"
      :component-paragraph="home.caseStudyOne.paragraph"/>

    <section class="py-10 bg-grey-lightest">
      <h1 class=" text-center text-4xl mb-12">{{ home.clients.title }}</h1>
      <div class=" container flex justify-around items-center flex-wrap mx-32">
        <img
          v-for="(org, index) in home.clients.organisation"
          :key="index"
          :name=" '' + index "
          :src="org.image"
          :alt="org.name"
          class="p-4 max-w-md w-48 ">
      </div>
    </section>

    <section class="py-10 bg-grey-lightest">
      <div class="max-w-md m-auto text-center">
        <h1 class="mt-0 mb-5 font-bold text-4xl leading-tight">{{ home.contactUs.title }}</h1>
        <p class="leading-normal pb-8">{{ home.contactUs.paragraph }}</p>
      </div>
      <div class="container l:flex justify-center">
        <div class=" bg-white p-10 m-5 mt-0 l:w-2/3 border-grey-lighter border-solid border-2 rounded-sm shadow">
          <appForm/>
        </div>
        <div class="bg-whiteback p-10  m-5 mt-0 l:w-1/3 border-grey-lighter border-solid border-2 rounded-sm shadow">
          <h2 class="leading-tight mt-2 mb-4 text-lg font-bold ">{{ home.contactUs.text1.header }}</h2>
          <p class="leading-normal ma-0 mb-4 f4 text-sm">{{ home.contactUs.text1.paragraph }}</p>
          <h2 class="leading-tight mt-2 mb-4 text-lg font-bold">{{ home.contactUs.text2.header }}</h2>
          <p class="leading-normal ma-0 f4 mb-4  text-sm">{{ home.contactUs.text2.paragraph }}</p>
          <h2 class="leading-tight mt-2 mb-4 text-lg font-bold">{{ home.contactUs.text3.header }}</h2>
          <p class="leading-normal ma-0 f4 text-sm">{{ home.contactUs.text3.paragraph }}</p>
        </div>
      </div>
    </section>
  </div>
</template>

<script>
import home from "~/content/home.json";

import appHeader from "~/components/Header.vue";
import splash from "~/components/Splash.vue";
import appForm from "~/components/Form.vue";
import appCaseStudy from "~/components/AppCaseStudy.vue";
import appFeatureBlock from "~/components/AppFeatureBlock.vue";


export default {
  components: {
    appHeader,
    splash,
    appForm,
    appCaseStudy,
    appFeatureBlock
  },
  data() {
    return {
      home
    };
  }
};
</script>

<style scoped lang="scss">
.pin-container {
  position: absolute;
  &-r {
    right: 4rem;
  }
}
</style>
