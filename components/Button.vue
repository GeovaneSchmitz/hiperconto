<template>
  <button
    :class="{ 'ph-button-active': active }"
    class="ph-button"
    @click="$emit('click', option)"
  >
    <slot></slot>
  </button>
</template>

<script lang="ts">
import { Prop, Component, Vue } from 'vue-property-decorator'

@Component
export default class PhButton extends Vue {
  @Prop() readonly option!: string

  active = false

  mounted() {
    this.$parent.$on('timeline-change', (eventOption: string) => {
      this.active = this.option === eventOption
    })
  }
}
</script>

<style lang="scss" scoped>
.ph-button {
  font-size: 12px;
  font-weight: 700;
  line-height: 1;
  font-family: 'Lato', sans-serif;
  margin: 0.5rem;
  border: 1px solid var(--primary-color);
  border-radius: 5px;
  padding: 1rem;
  color: rgba(0, 0, 0, 0.8);
  background-color: #fafafa;
  outline: none;
}

.ph-button:hover {
  color: var(--primary-color);
  background-color: var(--primary-color-background);
}

.ph-button:active,
.ph-button-active,
.ph-button:focus {
  color: #fff;
  background-color: var(--primary-color);
}
</style>
