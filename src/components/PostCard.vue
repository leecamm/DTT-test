<template>
  <section class="p-4 mt-7 rounded-lg shadow-lg bg-gray-50 w-80">
    <div class="h-32">
      <!-- <p class="mt-4 font-bold text-gray-600">{{ post.API }}</p> -->
      <a
        class="text-xl font-bold text-center text-green-800 hover:text-green-600 hover:underline"
        :href="post.url"
        target="_blank"
        rel="noreferrer"
      >
        {{ post.title }}
      </a>
      <p class="mt-2 text-justify text-gray-700">
        {{ post.description }}
      </p>
    </div>
  </section>
</template>

<script>

export default {
  props: {
    post: {
      type: Object,
      required: true,
    },
  },
}
</script>