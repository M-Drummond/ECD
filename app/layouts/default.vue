<template>
  <div class="overflow-x-hidden roboto-slab-regular">
    <!-- <svg
      class="divider absolute z-0 sm:mx-0 transform rotate-180 mt-0 mb-auto w-full"
      width="100%"
      viewBox="0 0 10 1"
    >
      <polygon stroke="none" stroke-width="0" fill="#efefef" points="0,0.6 0,1 10,1 10,0" />
    </svg> -->

    <main :class="[$route.name]" class="main relative z-10 px-4 md:px-0 mt-0 mb-auto">
      <site-header />
      <div class="h-4 md:h-6"></div>
      <div class="container mx-auto">
        <nuxt class="nuxt" />
      </div>
    </main>
    <div
         style="background-image: url('/images/uploads/ripples.png');"
         class="grid footer-cols grid-cols-1 md:grid-cols-3 px-4 py-8 mt-8 relative z-10">
      <div>
        <h4>Contact</h4>
        <div>
          <a
             class="bg-gray-400 hover:bg-gray-300 hover:underline p-8 uppercase inline-block my-4"
             href="tel:0412 829 262">
            Call Now
          </a>
          <a class="block" href="tel:0412 829 262">0412 829 262</a>
        </div>
      </div>
      <div>
        <h4>Address</h4>
        <div>
          <a
             class="bg-gray-400 hover:bg-gray-300 hover:underline p-8 uppercase inline-block my-4"
             href="https://www.google.com/maps/dir//ERIC+DRUMMOND+INFLATABLE+BOAT+REPAIR/data=!4m8!4m7!1m0!1m5!1m1!1s0x6b0d54a4cd16508f:0x454ab0dd19d5f4ee!2m2!1d151.311421!2d-33.6794363">
            Get Directions
          </a>
          <address>
            9 Darley St <br />
            Mona Vale 2103 <br />
            NSW, Australia
          </address>
        </div>
      </div>
      <div>
        <h4>Hours</h4>
        <ul>
          <li>
            Monday - Friday : 9:00am - 5:00pm
          </li>
          <li>
            Saturday : Closed, appointments available.
          </li>
          <li>
            Sunday : Closed, appointments available.
          </li>
        </ul>
      </div>
    </div>
    <site-footer />
  </div>
</template>

<style scoped>
.footer-cols {
  background: #efefef;
}

h4 {
  font-size: 1.25rem;
  font-weight: bold;
}

ul li {
  margin-bottom: 0.5rem;
}
</style>

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
