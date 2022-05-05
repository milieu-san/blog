<template>
  <iframe
    width="560"
    height="315"
    :src="url"
    title="YouTube video player"
    frameborder="0"
    allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture"
    allowfullscreen
  />
</template>

<script>
export default {
  name: 'YoutubePlayer',
  props: {
    id: {
      type: String,
      default: '',
      required: true
    }
  },
  computed: {
    url () {
      return `https://www.youtube.com/embed/${this.id}`
    }
  }
}
</script>
