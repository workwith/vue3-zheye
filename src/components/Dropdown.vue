<template>
  <div class="dropdown" ref="refdownDom">
    <a
      href="#"
      class="btn btn-outline-light my-2 dropdown-toggle"
      @click.prevent="IsOpen"
      >{{ `你好${name}` }}</a
    >
    <div class="dropdown-menu" :style="{ display: 'block' }" v-if="DownType">
      <slot></slot>
    </div>
  </div>
</template>

<script lang='ts'>
import { defineComponent, ref, onMounted, onUnmounted } from "vue";

export default defineComponent({
  name: "Dropdown",
  props: {
    name: {
      type: String,
      required: true,
    },
  },
  setup() {
    const DownType = ref(false);
    const refdownDom = ref<null | HTMLElement>(null);
    const IsOpen = () => {
      DownType.value = !DownType.value;
    };

    const handler = (e: MouseEvent) => {
      if (refdownDom.value) {
        if (
          !refdownDom.value.contains(e.target as HTMLElement) &&
          DownType.value
        ) {
          DownType.value = false;
        }
      }
    };
    onMounted(() => {
      document.addEventListener("click", handler);
    });
    onUnmounted(() => {
      document.removeEventListener("click", handler);
    });
    
    return {
      DownType,
      IsOpen,
      refdownDom,
    };
  },
});
</script>

<style>
</style>