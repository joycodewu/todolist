<template>
  <div class="myHeader">
    <input
      type="text"
      placeholder="请输入你的任务名称,按回车确认"
      @keyup.enter="addToto"
    />
  </div>
</template>

<script>
import {nanoid} from "nanoid"
export default {
  name: "myHeader",
  methods: {
    addToto(e) {
      if(e.target.value.trim()==='') return alert('不能为空')
      let newEvent={id:nanoid(),event:e.target.value,checked:false}
      this.recieve(newEvent);
      e.target.value=''
    },
  },
  props:['recieve']
};
</script>

<style lang='scss'>
.myHeader {
  width: 480px;
  padding: 5px 10px;
  // border: 1px solid gray;
  input {
    outline: none;
    border: 0;
    width: 460px;
    padding: 5px 10px;
    line-height: 15px;
    font-size: 15px;
    border: 1px solid lightgray;
  }
}
</style>