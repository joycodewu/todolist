<template >
  <div class="myFooter" v-if='events.length'>
    <div>
      <label><input type="checkbox" v-model="allSelected" /></label>
      <span>已完成{{ checkedLength }}</span>
      <span> / 全部{{ eventsLength }}</span>
    </div>
    <button @click="deleteAll">清除全部内容</button>
  </div>
</template>

<script>
export default {
  name: "myFooter",
  props: ["events","deleteAll"],
  methods:{

  },
  computed:{
    eventsLength(){
      return this.events.length
    },
    checkedLength(){
      return this.events.reduce((total,item)=>total+(item.checked?1:0),0)
    },
    allSelected:{
      get(){return this.checkedLength===this.eventsLength;},
      set(e){this.events.forEach(item=>{item.checked=e})}
      }  
    }
  }
  

</script>

<style lang='scss' scoped>
.myFooter {
  width: 480px;
  padding: 5px 10px;
  // border: 1px solid gray;
  span {
    margin-left: 15px;
  }
  display: flex;
  justify-content: space-between;
  align-items: center;
  button {
    background-color: rgb(226, 89, 68);
    border: 0;
    border-radius: 3px;
    padding: 5px 10px;
    font-size: 15px;
    color: white;
  }
}
</style>