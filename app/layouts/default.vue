<template>
  <div class="overflow-x-hidden roboto-slab-regular" style="background-color: #f7f9ff;">
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

    <section>
      <div class="container mx-auto markdown">
        <p class="text-sm mt-4 mb-0 uppercase">Map</p>
        <h2>Mona Vale, Sydney Location</h2>
      </div>
      <iframe
        title="map"
        src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d13288.488897822122!2d151.3214164113691!3d-33.68513792435382!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x6b0d54a4cd16508f%3A0x454ab0dd19d5f4ee!2sERIC%20DRUMMOND%20INFLATABLE%20BOAT%20REPAIR!5e0!3m2!1sen!2sau!4v1710810192427!5m2!1sen!2sau"
        width="600"
        height="450"
        style="border: 0;"
        allowfullscreen=""
        loading="lazy"
        referrerpolicy="no-referrer-when-downgrade"
        class="w-full min-h-[200px] relative z-30"
      ></iframe>
    </section>

    <div class="footer-cols">
      <div
        class="grid grid-cols-1 md:grid-cols-3 px-4 md:px-8 xl:px-0 py-8 mt-8 relative z-10 container mx-auto"
      >
        <div class="">
          <h4>Contact</h4>
          <div>
            <a
              class="bg-gray-400 hover:bg-gray-300 hover:underline p-8 uppercase inline-block my-4"
              href="tel:0412 829 262"
            >
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
              href="https://www.google.com/maps/dir//ERIC+DRUMMOND+INFLATABLE+BOAT+REPAIR/data=!4m8!4m7!1m0!1m5!1m1!1s0x6b0d54a4cd16508f:0x454ab0dd19d5f4ee!2m2!1d151.311421!2d-33.6794363"
            >
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
    </div>
    <site-footer />
  </div>
</template>

<style scoped>
.footer-cols {
  border-top: 1px solid navy;
  background: rgb(44, 82, 130);
  color: #fff;
}

h4 {
  color: inherit;
  font-size: 1.25rem;
  font-weight: bold;
}

ul li {
  margin-bottom: 0.5rem;
}

a {
  color: rgb(44, 82, 130);
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
export default class DefaultLayout extends Vue {}
</script>

<style lang="scss">
.divider {
  min-width: 100vw;
}

.nuxt {
  transition: all 0.5s cubic-bezier(0.55, 0, 0.1, 1);
}
</style>
