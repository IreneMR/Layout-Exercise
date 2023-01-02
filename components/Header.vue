<template>
  <header class="header">
    <div class="header__wrapper">
      <a href="/" class="icon icon-logo header__logo" />
      <nav class="header__nav">
        <span class="icon icon-menu header__menu-icon" @click="showMenu" />
        <ul ref="menu" class="header__menu">
          <li class="header__menu-item">
            <a href="#hero" class="header__anchor"> Hero </a>
          </li>
          <li class="header__menu-item">
            <a href="#about" class="header__anchor"> Quienes Somos </a>
          </li>
          <li class="header__menu-item">
            <a href="#services" class="header__anchor"> Servicios </a>
          </li>
          <li class="header__menu-item">
            <a href="#team" class="header__anchor"> Equipo </a>
          </li>
          <li class="header__menu-item">
            <a href="#newsletter" class="header__anchor"> Newsletter </a>
          </li>
          <li class="header__menu-item">
            <a href="#contact" class="header__anchor"> Contacto </a>
          </li>
        </ul>
      </nav>
    </div>
  </header>
</template>

<script lang="ts">
import { Component, Vue } from 'nuxt-property-decorator'
@Component
export default class Header extends Vue {
  showMenu(): void {
    ;(this.$refs.menu as HTMLDivElement)?.classList.toggle(
      'header__menu--visible'
    )
  }
}
</script>
