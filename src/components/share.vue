<template>
  <!-- 分享 -->
  <el-popover
    content="点击生成链接到剪贴板"
    placement="top"
    trigger="hover"
    width="180"
  >
    <Icon
      :data-clipboard-text="shareUrl"
      :size="20"
      @click="onSharePromptClick"
      class="mode-item"
      ref="shareIcon"
      slot="reference"
      type="share"
    />
  </el-popover>
</template>

<script type="text/ecmascript-6">
import Clipboard from "clipboard"
import { confirm } from "@/base/confirm"

export default {
  props: ["shareUrl"],
  mounted() {
    this.initShareIcon()
  },
  methods: {
    initShareIcon() {
      new Clipboard(this.$refs.shareIcon.$el)
    },
    onSharePromptClick() {
      confirm("分享链接已经复制到剪贴板，快去和小伙伴一起听歌吧！")
    }
  }
}
</script>
