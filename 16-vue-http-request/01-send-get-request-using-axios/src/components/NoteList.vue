<template>
  <div class="noteList">
    <div v-for="note in notes" class="note" :key="note.id">
      <h2>{{ note.title }}</h2>
      <article>
        <p>{{ note.content }}</p>
      </article>
    </div>
  </div>
</template>
<script setup>
defineProps(["notes"]);
</script>
<style scoped>
.noteList {
  margin: 48px 0;
  display: grid;
  row-gap: 48px;
  width: 100%;
}

.note h2 {
  font-weight: normal;
  margin-bottom: 12px;
}

.note article {
  color: hsl(0deg, 0%, 40%);
}
</style>
