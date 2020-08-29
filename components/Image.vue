<template>
  <div class="ph-image">
    <div class="ph-image-wrapper"><slot></slot></div>
    <div class="ph-image-description">{{ description }}</div>
  </div>
</template>

<script lang="ts">
import { Prop, Component, Vue } from 'vue-property-decorator'

@Component
export default class PhImage extends Vue {
  @Prop({ default: '' }) readonly description!: string
}
</script>

<style lang="scss">
.ph-image {
  display: flex;
  flex-direction: column;
  width: calc(100% + 4rem);
  margin: 0 -2rem;
  justify-content: center;
  align-items: center;
}

.ph-image-wrapper {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
}

.ph-image-wrapper > img {
  max-width: 100%;
  max-height: 100%;
  object-fit: cover;
  width: auto;
  height: auto;
}

.ph-image-description {
  margin: 0.5rem 0 2rem 0;
  color: var(--text-color-secundary);
  font-size: 14px;
  font-family: 'Lato', sans-serif;
  text-align: center;
}
</style>
