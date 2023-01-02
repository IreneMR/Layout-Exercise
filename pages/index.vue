<template>
  <main>
    <Hero />
  </main>
</template>

<script>
import { Component, Vue } from 'nuxt-property-decorator'
import Hero from '~/components/Hero.vue'
@Component({
  components: {
    Hero,
  },
})
export default class Home extends Vue {}
</script>
