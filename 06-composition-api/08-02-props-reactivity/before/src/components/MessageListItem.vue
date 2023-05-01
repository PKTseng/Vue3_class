<template>
  <li>{{ msg }}</li>

  <p>text</p>
</template>
<script>
import { ref, watch, watchEffect, toRefs } from "vue";

export default {
  props: ["msg", "text"],
  setup(props) {
    const { msg, text } = toRefs(props);
    console.log(msg);
    console.log(text);

    return {};
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
