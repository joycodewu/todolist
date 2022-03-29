<template>
  <div>
    <button @click="getAxios">11</button>
    <!-- 报错：无法对null读取code属性 -->
    <template  v-if="data">
      <div>code:{{ data.code }}</div>
      <div>message:{{ data.message }}</div>
      <div v-for='(item,index) in data.result' :key=index>
        <div>{{item.title}}</div>
        <div><img :src="item.image" alt=""></div>
        <div>{{item.passtime}}</div>
      </div>
    </template>
  </div>
</template>

<script>
export default {
  data() {
    return {
      data: null,
    };
  },
  methods: {
    getAxios() {
      console.log("axios请求数据中....");
      const url = "https://api.apiopen.top/getWangYiNews";
      this.axios.get(url).then((res) => {
        console.log(res);
        this.data = res.data;
      });
    },
  },
  // mounted(){
  //   console.log(this.axios)
  // }
};
</script>

<style>
div{
  text-overflow: ellipsis;
}
</style>