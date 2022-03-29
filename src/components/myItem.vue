<template>
  <div class='Item'>
    <div>
      <input type="checkbox" 
      :checked='myEvent.checked' 
      @click=getEventId(myEvent.id) 
      />
      <span>{{myEvent.event}}</span>
    </div>
    <button @click="delEventId(myEvent.id)">删除</button>
  </div>
</template>

<script>
export default {
  name: "myItem",
  props:['myEvent',"changeChecked","deleteEvent"],//用props接受父级组件的数据
  // mounted(){
  //   console.log(this.myEvent)
  // }
    methods:{
    getEventId(x){
      // console.log(x)
      this.changeChecked(x)
    },
    delEventId(x){
      this.deleteEvent(x)
    }
  }
};
</script>

<style lang='scss'>
.Item{
  &:hover{
    button{
      display: block;
    }
  }
  height: 25px;
  display: flex;
  justify-content: space-between;
  align-items: center;
  border-bottom: 1px solid black;
  padding: 10px;
  font-size:15px;
div{
  input{
      font-size:18px;
  }
  span{
    margin-left:15px ;
  }
}
  button{
    border:0 ;
    background-color: rgb(226, 89, 68);
    color: white;
    border-radius: 3px;
    padding: 3px 6px;
    font-size:15px;
    display: none;
    transition: 0.1s;
    width: 50px;
  }
}
</style>