<template>
  <div
    class="grid grid-cols-1 gap-6 mt-4 md:grid-cols-2 lg:grid-cols-3 2xl:grid-cols-4 justify-items-center"
  >
    <PostCard v-for="(post, index) in posts.slice(0, 10)" :key="index" :post="post" />
    
  </div>
</template>

<script>
import PostCard from "./PostCard.vue"
export default {
  props: {
    posts: {
      type: Array,
      required: true,
    },
  },
  components: {
    PostCard,
  },
}
</script>