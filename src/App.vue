<template>
  <Layout>
    <h2 class="mb-8 mt-16 text-4xl font-bold text-center capitalize">
      Post Section: <span class="text-green-700">{{ section }}</span>
    </h2>
    <h3 class="mt-8 font-light text-xl text-center">Choose Section</h3>
    <PostFilter v-model="section" :fetch="fetchPosts"/>
    <PostList :posts="posts" />
  </Layout>
</template>

<script>
import Layout from "./components/Layout.vue"
import PostFilter from "./components/PostFilter.vue"
import PostList from "./components/PostList.vue"

import axios from "axios"

export default {
  components: {
    Layout,
    PostFilter,
    PostList,
  },
  data() {
    return {
      section: "animals",
      posts: [],
    }
  },
  methods: {
    async fetchPosts(){
      try {
        const url = `https://api.publicapis.org/entries?category=${this.section}&https=true`
        const response = await axios.get(url)
        const results = response.data.entries
        this.posts = results.map(post => ({
          title: post.API,
          url: post.Link,
          description: post.Description,
        }))
      } catch (err) {
        if (err.response) {
          // client received an error response (5xx, 4xx)
          console.log("Server Error:", err)
        } else if (err.request) {
          // client never received a response, or request never left
          console.log("Network Error:", err)
        } else {
          console.log("Client Error:", err)
        }
      }
    },
  },
  mounted(){
    this.fetchPosts()
  },
}
</script>