<template>
  <li>{{ msg }}</li>
</template>
<script>
import { ref, watch, watchEffect } from "vue";

export default {
  props: ["msg"],

  setup(props) {
    // console.log(props);
    const { msg } = props;
    console.log(msg);
  },
};
</script>
<style scoped>
li {
  display: flex;
  align-items: center;
  gap: 12px;
}

li::before {
  content: "";
  display: block;
  width: 8px;
  height: 8px;
  background-color: hsl(280deg, 100%, 70%);
  border-radius: 100%;
}
</style>
