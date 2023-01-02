<template>
  <button ref="button" :class="computedStyleClass">
    <span class="button__text">
      {{ text }}
    </span>
  </button>
</template>

<script lang="ts">
import { Component, Prop, Vue } from 'nuxt-property-decorator'

@Component({
})
export default class Button extends Vue {
  @Prop({ required: true }) text!: string
  @Prop({ required: false, default: '' }) styleClass!: string

  get computedStyleClass () {
    return 'button ' + this.styleClass
  }
}
</script>
<style lang="scss">
@import "assets/components/button.scss";
</style>
