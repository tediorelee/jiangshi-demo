<template>
  <el-card
    class="box-card"
    shadow="always"
  >
    <!-- <h2>this is a card</h2> -->
    <el-row>
      <el-col :span="18">
        <el-input
          placeholder="请输入内容"
          v-model="inputName"
          clearable
        >
        </el-input>
      </el-col>
      <el-col :span="6">
        <el-button
          type="primary"
          @click="clickFun"
        >点我</el-button>
      </el-col>
    </el-row>
  </el-card>
</template>

<script lang="ts">
import { Component, Vue } from 'vue-property-decorator'

@Component({
  name: 'jiangShi'
})
export default class JiangShi extends Vue {
  inputName = ''
  TextEnum = '我是蒋师'

  created () {
    // todo
  }

  clickFun () {
    this.compareText()
  }

  compareText () {
    if (this.inputName === this.TextEnum) {
      this.$message({
        message: '恭喜你，这是一条成功消息',
        type: 'success'
      })
    } else {
      this.$message.error('错了哦，这是一条错误消息')
    }
  }
}
</script>

<style lang="less">
.box-card {
  width: 480px;
  margin: 0 auto;
}
</style>
