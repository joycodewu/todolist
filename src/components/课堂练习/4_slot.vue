<template>
  <div class="mySlot">
    <!-- 插槽：组建中的预留位，使用时可以进行替换 -->
    <div>
      <slot>
        <h2>这是标题A</h2>
        <p>杭州今天晴</p>
      </slot>
    </div>
    <div>
      <slot  name='two'>
        <h2>这是标题A</h2>
        <p>杭州今天晴</p>
      </slot>
    </div>
    <div>
      <slot name='three'>
        <h2>这是标题A</h2>
        <p>杭州今天晴</p>
      </slot>
    </div>
  </div>
</template>

<script>
export default {
  name: "mySlot",
};
</script>

<style lang='scss'>
.mySlot {
  >div {
    width: 300px;
    height: 300px;
    display: inline-block;
    overflow: hidden;
    &:first-child {
      background-color: lightblue;
    }
    &:nth-child(2) {
      background-color: antiquewhite;
    }
    &:last-child {
      background-color: yellowgreen;
    }
  }
}
</style>