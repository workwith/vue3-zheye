<template>
  <div class="row">
    <div class="col-4 mb-4" v-for="colum in columnlist" :key="colum.id">
      <div class="card h-100 shadow-sm">
        <div class="card-body text-center">
          <img
            :src="colum.avatar"
            class="rounded-circle border border-light w-25 my-3"
            :alt="colum.title"
          />
          <h5 class="card-title">{{ colum.title }}</h5>
          <p class="card-text text-left">{{ colum.description }}</p>
          <a href="#" class="btn btn-outline-primary">进入</a>
        </div>
      </div>
    </div>
  </div>
</template>

<script lang='ts'>
import { defineComponent, PropType, computed } from "vue";

export interface ColumnProps {
  id: number;
  title: string;
  avatar?: string;
  description: string;
}
export default defineComponent({
  name: "ColumnList",
  props: {
    list: {
      type: Array as PropType<ColumnProps[]>,
      required: true,
    },
  },
  setup(props) {
    const columnlist = computed(() => {
      return props.list.map((item) => {
        if (!item.avatar) {
          item.avatar = require("@/assets/column.jpg");
        }
        return item
      });
    });
    return {
      columnlist,
    };
  },
});
</script>

<style>
</style>