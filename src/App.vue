<template>
  <div class="container">
    <GloblHeader :user="user"></GloblHeader>
    <ColumnList :list="list"></ColumnList>
  </div>
</template>

<script lang="ts">
import { defineComponent } from "vue";
import "bootstrap/dist/css/bootstrap.min.css";
import ColumnList, { ColumnProps } from "@/components/ColumnList.vue";
import GloblHeader, { UserProps } from "@/components/GloblHeader.vue";

const testDate: ColumnProps[] = [
  {
    id: 1,
    title: "test1专栏",
    description: "我是内容",
    avatar:
      "https://img20.360buyimg.com/seckillcms/s280x280_jfs/t1/145313/34/18332/158153/5fd6db80E000c968d/face85e43dfc8c59.jpg.webp",
  },
  {
    id: 2,
    title: "test2专栏",
    description: "我是内容2",
  },
  {
    id: 3,
    title: "test2专栏",
    description: "我是内容2",
    avatar:
      "https://img20.360buyimg.com/seckillcms/s280x280_jfs/t1/145313/34/18332/158153/5fd6db80E000c968d/face85e43dfc8c59.jpg.webp",
  },
  {
    id: 4,
    title: "test2专栏",
    description: "我是内容2",
    avatar:
      "https://img20.360buyimg.com/seckillcms/s280x280_jfs/t1/145313/34/18332/158153/5fd6db80E000c968d/face85e43dfc8c59.jpg.webp",
  },
];
const userInfo: UserProps = {
  isLogin: true,
  name:'key',
  id:222
};

export default defineComponent({
  name: "App",
  components: {
    ColumnList,
    GloblHeader,
    
  },
  setup() {
    return {
      list: testDate,
      user: userInfo,
    };
  },
});
</script>

<style lang="scss">
// #app {
//   font-family: Avenir, Helvetica, Arial, sans-serif;
//   -webkit-font-smoothing: antialiased;
//   -moz-osx-font-smoothing: grayscale;
//   text-align: center;
//   color: #2c3e50;
//   margin-top: 60px;
// }
</style>
