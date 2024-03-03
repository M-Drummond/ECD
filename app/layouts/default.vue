<template>
  <div class="overflow-x-hidden">
    <svg
      class="divider absolute z-0 sm:mx-0 transform rotate-180 mt-0 mb-auto w-full"
      width="100%"
      viewBox="0 0 10 1"
    >
      <polygon stroke="none" stroke-width="0" fill="#efefef" points="0,0.6 0,1 10,1 10,0" />
    </svg>

    <main :class="[$route.name]" class="main relative z-10 px-4 md:px-0 mt-0 mb-auto">
      <div class="container mx-auto">
        <site-header />
        <nuxt class="nuxt" />
      </div>
    </main>
    <svg class="divider relative -mx-4 sm:mx-0" width="100%" viewBox="0 0 10 1">
      <polygon stroke="none" stroke-width="0" fill="#efefef" points="0,0.6 0,1 10,1 10,0" />
    </svg>
    <site-footer />
  </div>
</template>

<script lang="ts">
import { Component, Vue } from 'nuxt-property-decorator';
import SiteHeader from '@/components/partials/header.vue';
import SiteFooter from '@/components/partials/footer.vue';

@Component({
  components: {
    SiteHeader,
    SiteFooter,
  },
})
// eslint-disable-next-line prettier/prettier
export default class DefaultLayout extends Vue { }
</script>

<style lang="scss">
.divider {
  min-width: 100vw;
}

.nuxt {
  transition: all 0.5s cubic-bezier(0.55, 0, 0.1, 1);
}
</style>
