<template>
  <label>
    <span>搜索：</span>
    <input
      type="text"
      :value="searchText"
      @input="$emit('update:searchText', $event.target.value)"
    />
  </label>
  <label>
    <span>类别：</span>
    <select
      :value="category"
      @change="$emit('update:category', $event.target.value)"
    >
      <option value="default">默认</option>
      <option value="fontend">前端</option>
      <option value="backend">后端</option>
      <option value="fullstack">全栈</option>
    </select>
  </label>
</template>

<script>
export default {
  props: ["searchText", "category"],
  emits: ["update:searchText", "update:category"],
};
</script>
<style scoped>
input {
  padding: 8px 14px;
  border: 1px solid hsl(280deg, 50%, 50%);
  border-radius: 4px;
  outline: none;
  background: hsl(280deg, 50%, 30%, 0.2);
  color: white;
}
</style>
