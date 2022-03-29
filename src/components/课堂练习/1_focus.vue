<template>
  <div>

      <button @click=doFocus>点击测试</button>
      <input type="text" ref='x'>
      <hr>
      <input v-focus type="text"><br>
      <input type="text"><br>
      <input type="text"><br>
  </div>
</template>

<script>
export default {
    name:'myFocus',
    methods:{
        doFocus(){
            console.log(this.$refs.x)
            this.$refs.x.focus()
        }
    },

    directives:{
        focus:{
            //如果携程函数，就默认在DOM元素创建阶段触发
            //ctrl+i：可以查看提示
            bind(){
                console.log('bind:绑定阶段，在内存中创建')
            },
            inserted(el){
                console.log('inserted:出生阶段，显示在页面上')
                el.focus()

            }
        }
    }
}
</script>

<style scoped lang='scss'>
div{
    margin: 20px;
    padding: 10px;
    border: 1px solid black;
}
</style>