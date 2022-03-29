<template>
  <div
  class="el-tag"
  :class="{success:type=='success',info:type=='info',warning:type=='warning',danger:type=='danger'}">
    <!-- ElTag -->
    标签一
  </div>
</template>

<script>
export default {
  props: ["type"],
};
</script>

<style lang='scss'>
.el-tag {
  user-select: none;
  display: inline-block;
  padding: 10px 15px;
  background-color: #ecf5ff;
  color: #48a2ff;
  margin: 14px;
  border-radius: 4px;
  &.success {
    background-color: #f0f9eb;
    color: #67c23a;
  }
  &.info {
    background-color: #f4f4f5;
    color: #909399;
  }
  &.success {
    background-color: #fdf6ec;
    color: #e6a23d;
  }
}
</style>