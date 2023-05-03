<template>
  <div class="card">
    <MovieItem :description="movie.description"></MovieItem>
  </div>
</template>
<script>
import { provide, ref, toRef } from "vue"
import MovieItem from "./MovieItem.vue"
export default {
  components: {
    MovieItem,
  },
  setup() {
    const movie = ref({
      title: "电影",
      description: "这是一段电影的描述",
    })

    // Object Array 可以響應式
    // provide("movie", movie)

    // 基本型別不行
    provide("title", toRef(movie.value, "title")) //toRef 意思是從 movie 裡面抓 title 屬性

    setTimeout(() => {
      movie.value.title = "Movie"
    }, 1000)

    return { movie }
  },
}
</script>
<style scoped>
.card {
  padding: 12px;
  border: 1px solid hsl(240deg, 100%, 80%);
  border-radius: 4px;
}
</style>
