<template>

  <div class="container pt-4 flex justify-between items-center absolute pin-t w-full z-20">
    <app-logo
      :component-name="site.logo.name"
      :component-text="site.logo.text"
      :component-type="site.logo.type"/>
    <nav>
      <a
        v-for="(item, index) in site.nav"
        :key="`nav-${index}`"
        :href="item.href"
        class="text-white no-underline hover:text-point">
        {{ item.name }}
      </a>
    </nav>

  </div>

</template>

<script>
import site from "~/content/site.json";
import appLogo from "~/components/AppLogo.vue";

export default {
  components: {
    appLogo
  },
  data() {
    return {
      site
    };
  }
};
</script>

<style lang="scss">
@import "assets/scss/mixins";

nav {
  & > a {
    margin-right: 1rem;
    &:last-child {
      margin: 0;
    }
  }
}
</style>
