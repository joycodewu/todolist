<template>
  <div>
      <div class="my-menu">
          <span>首页</span>
          <span>关于我们</span>
          <span>商务合作</span>
          <span>产品介绍</span>
      </div>
  </div>
</template>

<script>
export default {
    name:"my-menu"
}
</script>

<style lang='scss'>
    .my-menu{
        background-color: #002c69;
        user-select: none;
        padding: 0 20px;
        span{
            display: inline-block;
            padding: 10px 20px;
            color: #fff;
            &:hover{
                background-color: #194788;
            }
        }
    }
</style>