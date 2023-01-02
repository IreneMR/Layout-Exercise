<template>
  <button v-if="to === ''" ref="button" :class="computedStyleClass">
    <Spinner v-if="spinner" ref="buttonSpinner" class="spinner-light" />
    <span v-if="iconClass !== ''" :class="'icon ' + iconClass" />
    <div class="text-container">
      <span class="button-text">
        {{ text }}
      </span>
      <span class="button-secondary-text">
        {{ secondaryText }}
      </span>
    </div>
  </button>
  <LinkContainer v-else class="link" :to="to" :absolute-url="absoluteUrl">
    <button ref="button" :class="computedStyleClass" :style="styleCode">
      <span v-if="iconClass !== ''" :class="'icon ' + iconClass" />
      <Spinner v-if="spinner" ref="buttonSpinner" class="spinner-light" />
      {{ text }}
    </button>
  </LinkContainer>
</template>

<script lang="ts">
import { Component, Prop, Vue } from 'nuxt-property-decorator'
import Spinner from '~/src/core/components/Spinner.vue'
import LinkContainer from '~/src/core/components/LinkContainer.vue'
@Component({
  components: { LinkContainer, Spinner }
})
export default class KadoButton extends Vue {
  @Prop({ required: true }) text!: string
  @Prop({ required: false, default: '' }) secondaryText!: string
  @Prop({ required: false, default: '' }) to!: string
  @Prop({ required: false, default: false }) absoluteUrl!: boolean
  @Prop({ required: false, default: false }) spinner!: boolean

  @Prop({ required: false, default: '' }) styleClass!: string
  @Prop({ required: false, default: '' }) styleCode!: string
  @Prop({ required: false, default: '' }) iconClass!: string
  @Prop({ required: false, default: false }) disabled!: boolean

  mounted () {
    this.stopLoading()
  }

  get computedStyleClass () {
    let styleClass = (this.styleClass.includes('kado-tag')) ? this.styleClass : 'kado-button ' + this.styleClass
    styleClass += (this.disabled) ? ' disabled' : ''
    return styleClass
  }

  startLoading () {
    (this.$refs.buttonSpinner as Spinner)?.startLoading()
    const button = (this.$refs.button as HTMLButtonElement)
    button.disabled = true
    button.style.pointerEvents = 'none'
  }

  stopLoading () {
    (this.$refs.buttonSpinner as Spinner)?.stopLoading()
    const button = (this.$refs.button as HTMLButtonElement)
    button.disabled = false
    button.style.pointerEvents = 'auto'
  }
}
</script>
<style lang="scss">
@import "assets/styles/components/buttons/KadoButton";
</style>
