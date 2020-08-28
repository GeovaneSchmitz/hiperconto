<template>
  <div class="ph-app">
    <div class="ph-content">
      <ph-title />
      <ph-image :discription="$t('imageDescription')" />
      <div class="ph-page"><Nuxt /></div>
    </div>
  </div>
</template>

<script lang="ts">
import Vue from 'vue'
import Image from '@/components/Image.vue'
import Title from '@/components/Title.vue'

export default Vue.extend({
  components: {
    phImage: Image,
    phTitle: Title,
  },
})
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
