<template>
  <div>
    <ph-text :text="$t('defaultHistory')" :first-letter="true" />
    <ph-footer
      ><nuxt-link to="/">
        <ph-button>{{ $t('linkHiper') }}</ph-button></nuxt-link
      ></ph-footer
    >
  </div>
</template>

<script lang="ts">
import { Component, Vue } from 'vue-property-decorator'

import PhText from '@/components/Text.vue'
import PhButton from '@/components/Button.vue'
import PhFooter from '@/components/Footer.vue'

@Component({
  transition: 'page',
  components: {
    PhText,
    PhFooter,
    PhButton,
  },
})
export default class PhDefaultHistory extends Vue {}
</script>
