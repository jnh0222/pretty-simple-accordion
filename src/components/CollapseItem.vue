<template>
  <div class="collapse-item" :class="userCollapseItemClass">
    <div class="collapse-head" :class="headActiveClass" @click="toggleShow">{{title}}</div>
    <div v-show="isContentShwoing" class="collapse-body">{{content}}</div>
  </div>
</template>

<script>
import Toggle from "./Toggle";

export default {
  name: "collapse-item",
  mixins: [Toggle],
  props: {
    title: { type: String, required: true },
    content: { type: String, required: true },
    collapseItemClass: {type: String, required: false }
  },
  computed: {
    isContentShwoing() {
      if(this.isShowing) {
        this.$emit("collapse-opened");
      } else {
        this.$emit("collapse-closed");
      }
      return this.isShowing;
    },
    userCollapseItemClass() {
      return this.collapseItemClass || null;
    },
    headActiveClass() {
      return this.isShowing ? "collapse-head--active" : null;
    },
  }
};
</script>

<style lang="scss" scoped>
.collapse-item {
  color: #333;
  line-height: 1.5;
  border: 1px solid #e5e5e5;
  & + .collapse-item {
    border-top: 0;
  }
  
}

.collapse-head,
.collapse-body {
  padding: 1em;
}

.collapse-head {
  background-color: #fff;
  cursor: pointer;
  &.collapse-head--active {
    background-color: #333;
    color: #fff;
    font-weight: bold;
  }
}

.collapse-body {
  border-top: 0;
}
</style>
