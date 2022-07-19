<script setup lang="ts">
import { ref } from 'vue'
import { ArrowRightIcon } from 'tdesign-icons-vue-next';

const news_input = ref('');

const onChange = (value) => {
  console.log('onChange：', value);
};

const count = ref(0)
</script>

<template>
  <div id="news">
    <t-button theme="primary" class="generate">
      开始生成
    </t-button>

    <div class="content">
      <div class="input">
        <t-textarea
            v-model="news_input"
            placeholder="请输入内容即可生成摘要"
            name="input"
            :autosize="{ minRows: 5, maxRows: 100 }"
            class="input_area"
            @change="onChange"
        />
      </div>
      <div class="generate_icon" style="display: flex;align-items: center;">
        <ArrowRightIcon size="40px" />
      </div>

      <div class="output">
        <t-textarea
            disabled
            default-value="生成摘要"
            name="output"
            :autosize="{ minRows: 5, maxRows: 100 }"
            class="output_area"
        />
      </div>
    </div>
  </div>
</template>

<style lang="less" scoped>
#news{
  height: 100vh;
  width: 100%;

  .generate{
    flex-wrap: wrap;
  }

  .content{
    display: flex;
    width: 100%;
  }
  .input{
    width: 50%;

    .input_area{
      left: 10%;
      width: 80%;
    }
  }
  .output{
    width: 50%;

    .output_area{
      left: 10%;
      width: 80%;
    }
  }
}
</style>
