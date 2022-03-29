<template>
  <div id="app">
    <myHeader :recieve="recieve" />
    <myList
      :events="events"
      :changeChecked="changeChecked"
      :deleteEvent="deleteEvent"
    />
    <myFooter :events="events" :deleteAll="deleteAll" />
  </div>
</template>

<script>
import myList from "./components/myList.vue";
import myFooter from "./components/myFooter.vue";
import myHeader from "./components/myHeader.vue";
// import {nanoid} from "nanoid"

export default {
  data() {
    return {
      events: [
        { id: "001", event: "抽烟", checked: true },
        { id: "002", event: "喝酒", checked: false },
        { id: "003", event: "烫头", checked: false },
      ],
    };
  },
  methods: {
    //接受并添加一个item
    recieve(x) {
      this.events.unshift(x);
    },
    //修改勾选状态
    changeChecked(x) {
      // console.log(x)
      this.events.forEach((event) => {
        if (event.id === x) event.checked = !event.checked;
      });
    },
    //删除一个事项
    deleteEvent(id) {
      if (confirm("确认要删除么?"))
        this.events = this.events.filter((event) => {
          return event.id != id;
        });
    },
    deleteAll() {
      this.events = this.events.filter((item) => {
        return !item.checked;
      });
    },
  },
  components: {
    myList,
    myFooter,
    myHeader,
  },
};
</script>

<style scoped>
#app {
  width: 500px;
  padding: 10px;
  border: 1px solid lightgray;
}
</style>