<template>
  <section class="section hero">
    <div class="section__wrapper hero__container">
      <img src="~/assets/images/hero-img.png" alt="" class="hero__image" />
      <img
        src="~/assets/images/bubble1.svg"
        alt=""
        class="hero__bubble hero__bubble--1"
      />
      <img
        src="~/assets/images/bubble2.svg"
        alt=""
        class="hero__bubble hero__bubble--2"
      />
      <img
        src="~/assets/images/bubble3.svg"
        alt=""
        class="hero__bubble hero__bubble--3"
      />
      <img
        src="~/assets/images/bubble4.svg"
        alt=""
        class="hero__bubble hero__bubble--4"
      />
      <div class="hero__info">
        <div ref="title" class="hero__title" @click="showInfo">
          <h1>Calidad, como cualidad</h1>
          <span ref="arrow" class="icon icon-arrow hero__arrow" />
        </div>
        <p ref="info" class="hero__subtitle">
          Diseño de experiencia de usuario Maquetación y diseño responsive
          Desarrollo por sprints
        </p>
        <div class="hero__buttons">
          <Button text="Empezar" style-class="button--green hero__button" />
          <Button text="Contacto" style-class="button--black hero__button" />
        </div>
      </div>
    </div>
  </section>
</template>

<script lang="ts">
import { Component, Vue } from 'nuxt-property-decorator'
import Button from '~/components/Button.vue'
@Component({
  components: {
    Button,
  },
})
export default class Hero extends Vue {
  showInfo(): void {
    ;(this.$refs.info as HTMLDivElement)?.classList.toggle(
      'hero__subtitle--active'
    )
    ;(this.$refs.title as HTMLDivElement)?.classList.toggle(
      'hero__title--active'
    )
    ;(this.$refs.arrow as HTMLDivElement)?.classList.toggle('hero__arrow--up')
  }
}
</script>
