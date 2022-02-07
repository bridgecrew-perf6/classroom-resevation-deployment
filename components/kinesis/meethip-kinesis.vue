<template>
  <kinesis-container class="parent d-flex justify-center">
    <kinesis-element
      class="pic meethip-1"
      :strength="-14"
      type="rotate"
      transformOrigin="50% 300%"
      axis="x"
    />
    <kinesis-element
      class="pic meethip-2"
      :strength="-7"
      type="rotate"
      transformOrigin="50% 300%"
      axis="x"
    />
    <kinesis-element
      class="pic meethip-3"
      :strength="14"
      type="rotate"
      transformOrigin="50% 300%"
      axis="x"
    />
    <kinesis-element
      class="pic meethip-4"
      :strength="7"
      type="rotate"
      transformOrigin="50% 300%"
      axis="x"
    />
    <kinesis-element
      class="pic meethip-5"
      :strength="0"
      type="depth"
      transformOrigin="50% 300%"
      axis="x"
    />
  </kinesis-container>
</template>

<script>
import { KinesisContainer, KinesisElement } from 'vue-kinesis'
export default {
  components: { KinesisContainer, KinesisElement },
}
</script>

<style lang="scss" scoped>
.parent {
  height: 80px;
}
.pic {
  height: 200px;
  position: absolute;
  background-size: contain;
  border-radius: 5px
}

.meethip-1 {
  background-image: url('../../assets/kinesis/meethip/1.jpg');
  width: 100px;
}
.meethip-2 {
  background-image: url('../../assets/kinesis/meethip/2.jpg');
  width: 100px;
}
.meethip-3 {
  background-image: url('../../assets/kinesis/meethip/3.jpg');
  width: 100px;
}
.meethip-4 {
  background-image: url('../../assets/kinesis/meethip/4.jpg');
  width: 100px;
}
.meethip-5 {
  background-image: url('../../assets/kinesis/meethip/5.jpg');
  width: 100px;
}
</style>
