<template>
  <div>
    <input type="text" placeholder="文字搜尋" v-model="searchText" />
    <ul>
      <li v-for="msg in searchTerm" :key="msg.id">{{ msg.content }}</li>
    </ul>
  </div>
</template>
<script>
import { ref, computed } from "vue";

export default {
  setup() {
    const messages = ref([
      { id: 1, content: "这是一条消息提醒112" },
      { id: 2, content: "这是一条消息提醒223" },
      { id: 3, content: "这是一条消息提醒334" },
      { id: 4, content: "这是一条消息提醒445" },
    ]);

    const searchText = ref("");

    const searchTerm = computed(() => {
      if (searchText.value === "") return messages.value;
      return messages.value.filter((msg) =>
        msg.content.includes(searchText.value)
      );
    });

    return { messages, searchTerm, searchText };
  },
};
</script>
<style scoped>
div {
  display: grid;
  place-items: center;
  gap: 24px;
}

p {
  margin: 12px 0 24px 0;
}

ul {
  list-style: none;
  display: grid;
  gap: 24px;
}

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
