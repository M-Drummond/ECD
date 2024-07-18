<template>
  <div>
    <section class="home">
      <div class="py-24 md:py-0 md:pb-24 grid grid-cols-1 md:grid-cols-2 md:gap-8">
        <div class="flex flex-col justify-center markdown">
          <p class="text-sm mt-4 mb-0">
            ABOUT
          </p>
          <h1>ERIC DRUMMOND INFLATABLE BOAT REPAIR</h1>
          <p>
            Based in Mona Vale and Servicing the Northern Beaches and the Greater Sydney Area, Eric
            Drummond Inflatable Boat Repairs specialises in repairs and servicing of all inflatables
            including:
          </p>
          <ul>
            <li>Surf Rescue and IRBs</li>
            <li>Recreational Watercraft</li>
            <li>Inflatable Kayaks</li>
            <li>Stand Up Paddle Boards</li>
            <li>Surf and Marine Rescue Craft</li>
            <li>All other inflatable products</li>
          </ul>
        </div>
        <div class="w-full flex flex-col items-center justify-center mb-8 md:mb-0">
          <img
            src="/images/uploads/hero.jpg"
            class="w-full h-auto mb-"
            alt="Eric Drummond Inflatable Boat Repair"
          />
        </div>
      </div>
      <div class="py-24 md:py-36 mx-auto grid grid-cols-1 md:grid-cols-2 md:gap-8">
        <div class="flex flex-col w-full">
          <img
            alt="Secondary Image"
            class="rounded shadow-xl"
            src="/images/uploads/melges.jpg"
            loading="lazy"
          />
        </div>

        <div class="flex flex-col w-full justify-center lg:items-start overflow-y-hidden">
          <div v-html="$md.render(welcomeText)" class="home__welcome markdown" />

          <div class="mb-12 xl:mb-0 w-full">
            <h4 v-if="isSignedUp">Thank you - we'll be in touch shortly.</h4>

            <form
              v-else
              @submit.prevent="handleSubmit"
              name="signups"
              data-netlify="true"
              class="flex flex-col items-center border-solid border-b-2 border-blue-400 py-2"
            >
              <label>Email Address</label>
              <input
                ref="emailInput"
                v-model="form.email"
                class="appearance-none mb-4 bg-transparent border-solid border-b-2 border-blue-400  w-full text-gray-700 mr-3 py-1 px-2 leading-tight focus:outline-none"
                type="text"
                name="email"
                placeholder="your@email.com"
                aria-label="Email address"
              />

              <label>Name</label>
              <input
                ref="name"
                v-model="form.name"
                class="appearance-none mb-4 bg-transparent border-solid border-b-2 border-blue-400  w-full text-gray-700 mr-3 py-1 px-2 leading-tight focus:outline-none"
                type="text"
                name="name"
                placeholder="John Smith"
                aria-label="Name"
              />
              
              <label>Phone</label>
              <input
                ref="name"
                v-model="form.phone"
                class="appearance-none mb-4 bg-transparent border-solid border-b-2 border-blue-400  w-full text-gray-700 mr-3 py-1 px-2 leading-tight focus:outline-none"
                type="text"
                name="name"
                placeholder="John Smith"
                aria-label="Name"
              />
              
              <label>Query</label>
              <textarea
                ref="name"
                v-model="form.query"
                class="appearance-none mb-36 bg-transparent border-solid border-2 border-blue-400  w-full text-gray-700 mr-3 py-1 px-2 leading-tight focus:outline-none"
                name="query"
                placeholder="I'd like help with ... "
                aria-label="Query"
              />

              
              <button
                class="bg-gray-400 hover:bg-gray-300 hover:underline py-2 px-4 uppercase inline-block my-4"
                type="submit"
              >
                Send
              </button>
            </form>
          </div>
        </div>
      </div>
    </section>
    <section id="gallery" class="py-24 md:py-36">
      <div class="markdown">
        <h2>Gallery</h2>
      </div>
      <div class="grid gap-8 grid-cols-2 md:grid-cols-4">
        <picture>
          <a href="/images/uploads/1.jpg" class="contents">
            <img src="/images/uploads/1.jpg" alt="gallery image" loading="lazy" />
            <span class="sr-only">Gallery Image - Inflatable Boat</span>
          </a>
        </picture>
        <picture>
          <a href="/images/uploads/2.jpg" class="contents">
            <img src="/images/uploads/2.jpg" alt="gallery image" loading="lazy" />
            <span class="sr-only">Gallery Image - Inflatable Boat</span>
          </a>
        </picture>
        <picture>
          <a href="/images/uploads/3.jpg" class="contents">
            <img src="/images/uploads/3.jpg" alt="gallery image" loading="lazy" />
            <span class="sr-only">Gallery Image - Inflatable Boat</span>
          </a>
        </picture>
        <picture>
          <a href="/images/uploads/4.jpg" class="contents">
            <img src="/images/uploads/4.jpg" alt="gallery image" loading="lazy" />
            <span class="sr-only">Gallery Image - Inflatable Boat</span>
          </a>
        </picture>
      </div>
    </section>
    <img
      src="/images/uploads/irb-vector.svg"
      alt="background image"
      loading="lazy"
      class="fixed top-auto bottom-0 left-0 right-0 z-0"
      style="opacity: 0.05;"
    />
  </div>
</template>

<style scoped>
section {
  position: relative;
  z-index: 10;
}

h1 {
  font-size: 32px;
  margin-top: 0;
  margin-bottom: 2rem;
  font-weight: 900;
}

p,
ul {
  line-height: 2.25rem;
}

p {
  max-width: 767px;
}

ul {
  list-style-type: disc;
  margin-left: 1.25rem;
}
</style>

<script lang="ts">
import { Component, Vue } from 'nuxt-property-decorator';
import settings from '@/content/settings/general.json';

export default class Home extends Vue {
  welcomeText = settings.welcomeText;

  get posts(): Post[] {
    return this.$store.state.posts;
  }
  
  

  isSignedUp = false;

  form = {
    email: '',
    phone: '',
    name: '',
    query: ''
  };

  encode(data): string {
    return Object.keys(data)
      .map((key) => `${encodeURIComponent(key)}=${encodeURIComponent(data[key])}`)
      .join('&');
  }

  validEmail(email): boolean {
    // eslint-disable-next-line
    const re = /^(([^<>()\[\]\\.,;:\s@"]+(\.[^<>()\[\]\\.,;:\s@"]+)*)|(".+"))@((\[[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}\])|(([a-zA-Z\-0-9]+\.)+[a-zA-Z]{2,}))$/;
    return re.test(email);
  }

  async handleSubmit(): Promise<void> {
    if (!this.validEmail(this.form.email)) {
      this.$refs.emailInput.focus();
      return;
    }

    try {
      await fetch('/', {
        method: 'POST',
        headers: { 'Content-Type': 'application/x-www-form-urlencoded' },
        body: this.encode({ 'form-name': 'signups', ...this.form }),
      });

      this.isSignedUp = true;
    } catch (error) {
      console.error(error);
    }
  }
}
</script>
