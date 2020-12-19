<template>
  <li class="dropdown-item"
  :class="{'disabled':disabled}">
    <slot></slot>
  </li>
</template>

<script lang='ts'>
import { defineComponent } from "vue";
export default defineComponent({
  name: "Dropdownitem",
  props:{
    disabled:{
      type: Boolean,
      defaule:false
    }
  }
});
</script>

<style>
</style>