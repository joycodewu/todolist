<template>
  <div>
      <div>{{a.title}}</div>
      <div>{{a.content}}</div>
  </div>
</template>

<script>
export default {
  name: "MyNews",
  props: ["a"],
  mounted() {
      console.log(this.a)
  },
};
</script>

<style>
</style>