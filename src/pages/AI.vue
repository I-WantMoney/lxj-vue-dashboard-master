<template>
  <div>
  <input id="check1" class="check" type="radio" name="ai" />
  <label class="label" for="check1"> Translate - Amazon Translate </label>
  <div class="content">
    <TranslateText />
  </div>

  <input id="check4" class="check" type="radio" name="ai" />
  <label class="label" for="check4"> Interpret Text - Amazon Comprehend </label>
  <div class="content">
    <InterpretText />
  </div>

  <input id="check5" class="check" type="radio" name="ai" />
  <label class="label" for="check5"> Text to Speech - Amazon Polly </label>
  <div class="content">
    <!-- 追加 1-->
    <TextSpeech />
  </div>
  </div>
</template>

<script>
import TranslateText from '@/components/TranslateText.vue';

import InterpretText from '@/components/InterpretText.vue';
// 追加 2
import TextSpeech from '@/components/TextSpeech.vue';

export default {
  components: {
    TranslateText,
    InterpretText,
    // 追加 3
    TextSpeech,
  },
};
</script>

