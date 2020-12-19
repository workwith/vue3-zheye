<template>
  <nav class="navbar navbar-dark bg-primary justify-content-between mb-4">
    <a class="navbar-brand" href="#">者也专栏</a>
    <ul v-if="!user.isLogin" class="list-inline mb-0">
      <li class="list-inline-item">
        <a href="#" class="btn btn-outline-light my-2">登录</a>
      </li>
      <li class="list-inline-item">
        <a href="#" class="btn btn-outline-light my-2">注册</a>
      </li>
    </ul>
    <ul v-else class="list-inline mb-0">
      <li class="list-inline-item">
        <Dropdown :name="user.name">
          <Dropdownitem><a class="dropdown-item" href="#">新建文件</a></Dropdownitem>
          <Dropdownitem disabled><a class="dropdown-item" href="#">新建文件</a></Dropdownitem>
          <Dropdownitem><a class="dropdown-item" href="#">新建文件</a></Dropdownitem>
        </Dropdown>
      </li>
    </ul>
  </nav>
</template>

<script lang='ts'>
import { defineComponent, PropType } from "vue";
import Dropdown from "@/components/Dropdown.vue";
import Dropdownitem from "@/components/Dropdownitem.vue";

export interface UserProps {
  isLogin: boolean;
  name?: string;
  id?: number;
}
export default defineComponent({
  name: "GloblHeader",
  components: {
    Dropdown,
    Dropdownitem,
  },
  props: {
    user: {
      type: Object as PropType<UserProps>,
      required: true,
    },
  },
});
</script>

<style>
</style>