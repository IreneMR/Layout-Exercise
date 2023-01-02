<template>
  <header class="header">
    <div class="header__wrapper">
      <span class="icon icon-logo logo" />
      <nav class="nav">
        <span
          class="icon icon-menu menu__icon"
          @click="showMenu"
        />
        <ul ref="menu" class="menu">
          <li class="menu__item">
            <a href="#hero">Hero</a>
          </li>
          <li class="menu__item">
            <a href="#about">Quienes Somos</a>
          </li>
          <li class="menu__item">
            <a href="#services">Servicios</a>
          </li>
          <li class="menu__item">
            <a href="#team">Equipo</a>
          </li>
          <li class="menu__item">
            <a href="#newsletter">Newsletter</a>
          </li>
          <li class="menu__item">
            <a href="#contact">Contacto</a>
          </li>
        </ul>
      </nav>
    </div>
  </header>
</template>

<script lang="ts">
import {Component, Vue} from 'nuxt-property-decorator'
@Component
export default class Header extends Vue {
  showMenu () : void {
    (this.$refs.menu as HTMLDivElement)?.classList.toggle('is-visible');
  }
}
</script>
<style lang="scss" scoped>
@import "../assets/components/header";
</style>

