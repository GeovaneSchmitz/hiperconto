<template>
  <div>
    <ph-text :text="$t('defaultHistory')" :first-letter="true" />
    <ph-footer
      ><nuxt-link to="/"> {{ $t('linkHiper') }}</nuxt-link></ph-footer
    >
  </div>
</template>

<script lang="ts">
import { Component, Vue } from 'vue-property-decorator'

import PhText from '@/components/Text.vue'
import PhFooter from '@/components/Footer.vue'

@Component({
  transition: 'page',
  components: {
    PhText,
    PhFooter,
  },
})
export default class PhDefaultHistory extends Vue {}
</script>
