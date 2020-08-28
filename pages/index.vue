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
import Vue from 'vue'
import Text from '@/components/Text.vue'
import Question from '@/components/Question.vue'
import Footer from '@/components/Footer.vue'
import Timeline from '@/components/Timeline.vue'
import Button from '@/components/Button.vue'

export default Vue.extend({
  transition: 'page',
  components: {
    phText: Text,
    phTimeline: Timeline,
    phQuestion: Question,
    phFooter: Footer,
    phButton: Button,
  },
})
</script>
