<template>
<article>
  <veui-button
    ref="a"
    @click="aOpen = !aOpen"
  >
    Toggle A
  </veui-button>
  <veui-overlay
    target="a"
    position="top-start"
    :open.sync="aOpen"
    overlay-class="relative-overlay"
  >
    A
  </veui-overlay>

  <veui-button
    ref="b"
    @click="bOpen = !bOpen"
  >
    Toggle B
  </veui-button>
  <veui-overlay
    target="b"
    position="top-start"
    :open.sync="bOpen"
    overlay-class="relative-overlay"
  >
    B
    <veui-button
      ref="b-a"
      ui="s"
      @click="bAOpen = !bAOpen"
    >
      Toggle B-A
    </veui-button>
    <veui-overlay
      target="b-a"
      position="top-start"
      :open.sync="bAOpen"
      overlay-class="relative-overlay"
    >
      B-A
    </veui-overlay>
  </veui-overlay>

  <veui-button
    ref="c"
    @click="cOpen = !cOpen"
  >
    Toggle C
  </veui-button>
  <veui-overlay
    target="c"
    position="top-start"
    :open.sync="cOpen"
    overlay-class="relative-overlay"
  >
    C
  </veui-overlay>
  <veui-button
    ui="xs"
    @click="aOpen = bOpen = cOpen = bAOpen = false"
  >
    Hide all
  </veui-button>
</article>
</template>

<script>
import { Overlay, Button } from 'veui'

export default {
  components: {
    'veui-overlay': Overlay,
    'veui-button': Button
  },
  data () {
    return {
      aOpen: false,
      bOpen: false,
      cOpen: false,
      bAOpen: false
    }
  }
}
</script>

<style lang="less" scoped>
.veui-overlay {
  display: none;
}

.relative-overlay {
  width: 200px;
  height: 100px;
  line-height: 100px;
  text-align: center;
  border: 1px solid #dbdbdb;
  background-color: #fff;

  .veui-button {
    margin-left: 10px;
  }
}
</style>
