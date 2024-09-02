<template>
  <header style="background-color: #2c5282;"
    class="flex flex-col md:flex-row items-center justify-between w-full py-4 md:py-8 px-4 bg-opacity-25 relative z-20 bg-blue-800 text-white w-screen">
    <div class="header__logo  relative">
      <nuxt-link to="/"
        class="flex flex-row space-x-4 reative py-4 group text-2xl font-black uppercase hover:underline">
        Eric Drummond Inflatable Boat Repair
      </nuxt-link>
    </div>

    <a class="inline-flex flex-row phone" href="tel:0412 829 262">

      <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor"
        class="size-4 mr-2 w-4">
        <path stroke-linecap="round" stroke-linejoin="round"
          d="M2.25 6.75c0 8.284 6.716 15 15 15h2.25a2.25 2.25 0 0 0 2.25-2.25v-1.372c0-.516-.351-.966-.852-1.091l-4.423-1.106c-.44-.11-.902.055-1.173.417l-.97 1.293c-.282.376-.769.542-1.21.38a12.035 12.035 0 0 1-7.143-7.143c-.162-.441.004-.928.38-1.21l1.293-.97c.363-.271.527-.734.417-1.173L6.963 3.102a1.125 1.125 0 0 0-1.091-.852H4.5A2.25 2.25 0 0 0 2.25 4.5v2.25Z" />
      </svg>


      0412 829 262</a>
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
  ul li>a {
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

a.phone {
  padding-right: 1rem;
}

</style>
