<template>
  <footer class="footer -mx-4 md:mx-0">
    <div class="container mx-auto py-6 flex justify-center">
      &copy; 2024 ECD Inflatables
    </div>
  </footer>
</template>

<script lang="ts">
import { Component, Vue } from 'nuxt-property-decorator';

@Component
export default class Footer extends Vue {}
</script>

<style lang="scss">
.footer {
  background-color: #fffafa;
}
</style>
