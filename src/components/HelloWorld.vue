<template>
  <div class="hello">
    <n-space vertical>
      <n-input v-model:value="value" type="text" rows="4">
        <template #prefix>
          [root@vmhost {{currDir}}]#
        </template>
      </n-input>

      <n-upload action="https://www.mocky.io/v2/5e4bafc63100007100d8b70f">
        <n-upload-dragger>
          <div style="margin-bottom: 12px;">
            <n-icon size="48" :depth="3">
              <archive-icon />
            </n-icon>
          </div>
          <n-text style="font-size: 16px;">点击或者拖动文件到该区域来上传</n-text>
          <n-p depth="3" style="margin: 8px 0 0 0;"
            >请不要上传敏感数据，比如你的银行卡号和密码，信用卡号有效期和安全码</n-p
          >
        </n-upload-dragger>
      </n-upload>
    </n-space>
    <h1>{{ msg }}</h1>
  </div>
</template>

<script>
import {NInput, NSpace, NUpload, NUploadDragger, NText, NP, NIcon} from 'naive-ui';
import {ref} from 'vue';
import {ArchiveOutline as ArchiveIcon} from '@vicons/ionicons5'
export default {
  name: 'HelloWorld',
  props: {
    msg: String
  },
  setup() {
    return {
      value: ref(null),
      currDir: ref('~')
    }
  },
  components: {NInput, NSpace, ArchiveIcon, NUpload, NUploadDragger, NText, NP, NIcon}
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
