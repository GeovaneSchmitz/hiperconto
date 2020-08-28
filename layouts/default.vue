<template>
  <div class="ph-app">
    <div class="ph-content">
      <ph-title />
      <ph-image :description="$t('imageDescription')" />
      <div class="ph-page"><Nuxt /></div>
    </div>
  </div>
</template>

<script lang="ts">
import PhImage from '@/components/Image.vue'
import PhTitle from '@/components/Title.vue'

import { Component, Vue } from 'vue-property-decorator'

@Component({
  components: {
    PhImage,
    PhTitle,
  },
})
export default class phLayout extends Vue {}
</script>

<style lang="scss">
* {
  font-family: 'Merriweather', serif;
}
$primary: #eb415a;
body {
  --primary-color: #{$primary};
  --primary-color-background: #{adjust-color($primary, $alpha: -0.9)};
  --primary-color-darker: #{adjust-color($primary, $lightness: -20)};
  --element-color: #fafafa;
  --text-color: rgba(0, 0, 0, 0.8);
  --text-color-secundary: rgba(0, 0, 0, 0.6);
  --box-shadow-color: rgba(0, 0, 0, 0.1);
  --highlight-color: #000;

  background-color: #fafaf0;
  margin: 0;
  padding: 0;
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
