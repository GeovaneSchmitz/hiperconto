<template>
  <div class="ph-image">
    <div class="ph-image-wrapper">
      <img class="ph-image-img" src="~/assets/bale-das-mulheres-bruxas.jpg" />
    </div>
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

<style lang="scss" scoped>
.ph-image {
  display: flex;
  flex-direction: column;
  width: calc(100% + 4rem);
  margin: 0 -2rem;
}
.ph-image-wrapper {
  overflow: hidden;
  max-height: 600px;
}
.ph-image-description {
  margin: 0.5rem 0 2rem 0;
  color: var(--text-color-secundary);
  font-size: 14px;
  font-family: 'Lato', sans-serif;
  text-align: center;
}
.ph-image-img {
  max-width: 110%;
  object-fit: cover;
  width: auto;
  height: auto;
}
</style>
