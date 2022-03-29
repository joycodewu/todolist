<template>
  <div class="myList">
    <div>
      <myItem 
      v-for="event in events" 
      :key="event.id" 
      :myEvent="event"
      :changeChecked="changeChecked" 
      :deleteEvent="deleteEvent"
       />
    </div>
  </div>
</template>

<script>
import myItem from "./myItem.vue";
export default {
  name: "myList",
  data() {
    return {};
  },
  props: ["events","changeChecked","deleteEvent"],
  components: {
    myItem,
  },

};
</script>

<style scoped lang='scss'>
.myList {
  // border: 1px solid gray;
  width: 500px;
  height: 220px;
  display: flex;
  justify-content: center;
  overflow: auto;
  // overflow-x:hidden ;
  // align-items: center;
  > div {
    width: 480px;
    border: 1px solid gray;
  }
}
</style>
