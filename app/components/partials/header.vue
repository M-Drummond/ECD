<template>
  <header
    style="background-color: #2c5282;"
    class="flex items-center justify-center py-4 md:py-8 px-4 xl:px-0 bg-opacity-25 relative z-20 bg-blue-800 text-white w-screen"
  >
    <div class="header__logo pl-4 relative">
      <nuxt-link
        to="/"
        class="flex flex-row space-x-4 reative py-4 group text-2xl font-black uppercase hover:underline"
      >
        <!-- <img
          src="/images/uploads/irb-vector.svg"
          alt="background image"
          loading="lazy"
          class="z-10 block w-8 h-8 mr-2 inset-0 opacity-10"
          style="transform: scaleX(-1);"
        /> -->
        Eric Drummond Inflatable Boat Repair
      </nuxt-link>
    </div>

    <!-- <nav class="nav ml-auto">
      <ul class="flex flex-row items-center sm:mt-4 sm:pt-4 md:mt-0 md:pt-0 md:mr-4 lg:mr-8">
        <li>
          <nuxt-link to="/blog" class="block font-medium px-4 py-1 md:p-2 lg:px-4">
            Blog
          </nuxt-link>
        </li>

        <li
          v-for="(page, index) in pages"
          :key="index"
          class="block font-medium px-4 py-1 md:p-2 lg:px-4"
        >
          <nuxt-link :to="`/${page.slug}`">{{ page.title }}</nuxt-link>
        </li>
      </ul>
    </nav> -->
  </header>
</template>

<script lang="ts">
import { Component, Vue } from 'nuxt-property-decorator';
import settings from '@/content/settings/general.json';

@Component
export default class Header extends Vue {
  get pages(): Page[] {
    return this.$store.state.pages;
  }

  logo = settings.logo;
}
</script>

<style lang="scss">
header {
  box-shadow: 0 2px 1px 0px rgba(0, 0, 0, 0.125);
  letter-spacing: 0.125rem;
}

.nav {
  ul li > a {
    &.nuxt-link-active {
      color: $bluise;
      @apply font-bold;
    }
  }
}

.header__logo img {
  // opacity: 0.125;
  transition: 0.25s ease-in opacity;
}

.header__logo:hover img {
  // opacity: 0.0125;
}
</style>
