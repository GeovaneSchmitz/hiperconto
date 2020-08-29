<template>
  <div>
    <div class="ph-title">
      {{ $t('title') }}
    </div>
    <div class="ph-subtitle">
      {{ $t('subtitle') }} - {{ $t('authorOriginal') }}
    </div>
  </div>
</template>

<script lang="ts">
import { Component, Vue } from 'vue-property-decorator'

@Component
export default class PhTitle extends Vue {}
</script>

<style lang="scss" scoped>
.ph-title {
  font-size: 3rem;
  font-weight: 700;
  line-height: 1;
  margin-top: 2rem;
  color: var(--primary-color);
}

.ph-subtitle {
  margin: 0;
  line-height: 1;
  font-weight: 400;
  color: var(--text-color-secundary);
  font-family: 'Lato', sans-serif;
}
</style>
