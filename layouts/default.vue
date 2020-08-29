<template>
  <div class="ph-app">
    <div class="ph-content">
      <ph-title />
      <ph-authors />
      <ph-image :description="$t('imageDescription')"
        ><img src="~/assets/bale-das-mulheres-bruxas.jpg"
      /></ph-image>
      <div class="ph-page"><Nuxt /></div>
    </div>
  </div>
</template>

<script lang="ts">
import { Component, Vue } from 'vue-property-decorator'

import PhImage from '@/components/Image.vue'
import PhTitle from '@/components/Title.vue'
import PhAuthors from '@/components/Authors.vue'

@Component({
  components: {
    PhImage,
    PhTitle,
    PhAuthors,
  },
})
export default class phLayout extends Vue {}
</script>

<style lang="scss">
$primary: #6b2b83;

* {
  font-family: 'Merriweather', serif;
}

body {
  --primary-color: #{$primary};
  --primary-color-background: #{adjust-color($primary, $alpha: -0.8)};
  --primary-color-select: #{adjust-color(
      $primary,
      $lightness: -20,
      $alpha: -0.2
    )};
  --primary-color-darker: #{adjust-color($primary, $lightness: -20)};
  --element-color: #222;
  --text-color: rgba(255, 255, 255, 0.9);
  --text-color-secundary: rgba(255, 255, 255, 0.6);
  --box-shadow-color: rgba(0, 0, 0, 0.1);
  --highlight-color: #222;

  background-color: #2a2b29;
  margin: 0;
  padding: 0;
}

*::selection {
  background: var(--primary-color-select);
}

.ph-app {
  display: flex;
  flex-direction: column;
  align-items: center;
}

.ph-content {
  padding: 1rem 4rem;
  max-width: 720px;
}

@media screen and (max-width: 720px) {
  .ph-content {
    padding: 1rem 2rem;
    max-width: 720px;
  }
}

.ph-page {
  display: flex;
  flex-direction: column;
}
</style>
