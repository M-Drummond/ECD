<template>
  <header
    class="flex items-center py-4 md:py-8 px-4 xl:px-0 bg-opacity-25 relative z-10 shadow-md bg-white w-screen"
  >
    <div class="header__logo pl-4 relative">
      <nuxt-link to="/" class="flex flex-row space-x-4 reative py-4 group">
        <img
          src="/images/uploads/irb-vector.svg"
          alt="background image"
          loading="lazy"
          class="z-10 block w-12 h-12 absolute inset-0 w-full h-full opacity-10"
          style="transform: scaleX(-1);"
        />
        Eric Drummond Inflatable Boat Repair
      </nuxt-link>
    </div>

    <nav class="nav ml-auto">
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
    </nav>
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
.nav {
  ul li > a {
    &.nuxt-link-active {
      color: $bluise;
      @apply font-bold;
    }
  }
}

.header__logo img {
  opacity: 0.125;
  transition: 0.25s ease-in opacity;
}

.header__logo:hover img {
  opacity: 0.0125;
}
</style>
