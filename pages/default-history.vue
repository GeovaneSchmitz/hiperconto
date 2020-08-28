<template>
  <div>
    <ph-text :text="$t('defaultHistory')" :first-letter="true" />
    <ph-footer
      ><nuxt-link to="/"> {{ $t('linkHiper') }}</nuxt-link></ph-footer
    >
  </div>
</template>

<script lang="ts">
import Vue from 'vue'
import Text from '@/components/Text.vue'
import Footer from '@/components/Footer.vue'

export default Vue.extend({
  transition: 'page',
  components: {
    phText: Text,
    phFooter: Footer,
  },
})
</script>
