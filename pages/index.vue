<template>
  <div>
    <div class="ph-block">
      <ph-text :text="$t('introduction')" :first-letter="true" />
    </div>
    <ph-question>
      <template v-slot:question>{{ $t('question1') }} </template>
      <template v-slot:buttons>
        <ph-button option="1">{{ $t('question1Option1') }}</ph-button>
        <ph-button option="2">{{ $t('question1Option2') }}</ph-button>
        <ph-button option="3">{{ $t('question1Option3') }}</ph-button>
      </template>
      <template v-slot:timeline>
        <ph-timeline option="1">
          <ph-text :text="$t('timelineQuestion1Option1')" />
        </ph-timeline>
        <ph-timeline option="2">
          <ph-text :text="$t('timelineQuestion1Option2')" />
          <ph-question>
            <template v-slot:question>{{ $t('question2') }} </template>
            <template v-slot:buttons>
              <ph-button option="1">{{ $t('question2Option1') }}</ph-button>
              <ph-button option="2">{{ $t('question2Option2') }}</ph-button>
            </template>
            <template v-slot:timeline>
              <ph-timeline option="1">
                <ph-question>
                  <template v-slot:question>{{ $t('question3') }} </template>
                  <template v-slot:buttons>
                    <ph-button option="1">{{ $t('yes') }}</ph-button>
                    <ph-button option="2">{{ $t('no') }}</ph-button>
                  </template>
                  <template v-slot:timeline>
                    <ph-timeline option="1">
                      <ph-text :text="$t('timelineQuestion3Option1')" />
                    </ph-timeline>
                    <ph-timeline option="2">
                      <ph-text :text="$t('timelineQuestion3Option2')" />
                      <ph-text :text="$t('timelineEnd')" />
                    </ph-timeline>
                  </template>
                </ph-question>
              </ph-timeline>
              <ph-timeline option="2">
                <ph-question>
                  <template v-slot:question>{{ $t('question4') }} </template>
                  <template v-slot:buttons>
                    <ph-button option="1">{{ $t('yes') }}</ph-button>
                    <ph-button option="2">{{ $t('no') }}</ph-button>
                  </template>
                  <template v-slot:timeline>
                    <ph-timeline option="1">
                      <ph-text :text="$t('timelineQuestion4Option1')" />
                    </ph-timeline>
                    <ph-timeline option="2">
                      <ph-text :text="$t('timelineQuestion4Option2')" />
                      <ph-text :text="$t('timelineEnd')" />
                    </ph-timeline>
                  </template>
                </ph-question>
              </ph-timeline>
            </template>
          </ph-question>
        </ph-timeline>
        <ph-timeline option="3">
          <ph-text :text="$t('timelineQuestion1Option3')" />
          <ph-text :text="$t('timelineEnd')" />
        </ph-timeline>
      </template>
    </ph-question>
    <ph-footer
      ><nuxt-link to="default-history">
        {{ $t('linkDefaultHistory') }}</nuxt-link
      ></ph-footer
    >
  </div>
</template>

<script lang="ts">
import PhText from '@/components/Text.vue'
import PhQuestion from '@/components/Question.vue'
import PhFooter from '@/components/Footer.vue'
import PhTimeline from '@/components/Timeline.vue'
import PhButton from '@/components/Button.vue'

import { Component, Vue } from 'vue-property-decorator'

@Component({
  transition: 'page',
  components: {
    PhText,
    PhTimeline,
    PhQuestion,
    PhFooter,
    PhButton,
  },
})
export default class PhHyperConto extends Vue {}
</script>
