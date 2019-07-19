<template>
  <div class="simple-collapse-item" :class="userCollapseItemClass" :ref="simpleId">
    <div class="simple-collapse-head" :class="headActiveClass" @click="toggleShowing">{{title}}</div>
    <div v-show="isShowing" class="simple-collapse-body">{{content}}</div>
    <!-- <div v-show="isContentShowing" class="simple-collapse-body">{{content}}</div> -->
  </div>
</template>

<script>
import Toggle from "./Toggle";

export default {
  name: "simple-collapse",
  mixins: [Toggle],
  props: {
    title: { type: String, required: true },
    content: { type: String, required: true },
    collapseItemClass: {type: String, required: false },
    simpleId: {type: String, required: false, default: null}
  },
  updated() {
      if(this.isShowing) {
        this.$emit("simple-collapse-opened", this.simpleId);
      } else {
        this.$emit("simple-collapse-closed", this.simpleId);
      }
    },
  computed: {
    userCollapseItemClass() {
      return this.collapseItemClass || null;
    },
    headActiveClass() {
      return this.isShowing ? "simple-collapse-head--active" : null;
    },
  }
};
</script>

<style lang="scss" scoped>
.simple-collapse-item {
  color: #333;
  line-height: 1.5;
  border: 1px solid #e5e5e5;
  & + .simple-collapse-item {
    border-top: 0;
  }
  
}

.simple-collapse-head,
.simple-collapse-body {
  padding: 1em;
}

.simple-collapse-head {
  background-color: #fff;
  cursor: pointer;
  &.simple-collapse-head--active {
    background-color: #333;
    color: #fff;
    font-weight: bold;
  }
}

.simple-collapse-body {
  border-top: 0;
}
</style>
