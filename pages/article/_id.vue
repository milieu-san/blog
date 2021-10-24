<template>
  <div class="container blog-content">
    <div class="hero">
      <div class="hero-body">
        <div class="container is-max-desktop">
          <p class="title">
            {{ article.title }}
          </p>
        </div>
      </div>
    </div>
    <div class="section pt-1">
      <div class="container is-max-desktop">
        <nuxt-content :document="article" />
      </div>
    </div>
  </div>
</template>

<script>
export default {
  async asyncData ({ $content, params }) {
    const article = await $content('articles', params.id).fetch()

    return {
      article
    }
  }
}
</script>

<style scoped>
.blog-content * {
  font-family: "Source Code Pro", Monaco, monospace;
}

.nuxt-content ul {
  margin: 1em 0;
  padding-left: 40px;
  list-style-type: disc;
}

.nuxt-content ol {
  margin: 1em 0;
  padding-left: 40px;
  list-style-type: decimal;
}

.nuxt-content h1 {
  display: block;
  font-size: 2em;
  -webkit-margin-before: 0.67em;
  -webkit-margin-after: 0.67em;
  -webkit-margin-start: 0px;
  -webkit-margin-end: 0px;
  font-weight: bold;
}

.nuxt-content h2 {
  display: block;
  font-size: 1.5em;
  -webkit-margin-before: 0.83em;
  -webkit-margin-after: 0.83em;
  -webkit-margin-start: 0px;
  -webkit-margin-end: 0px;
  font-weight: bold;
}

.nuxt-content h3 {
  display: block;
  font-size: 1.17em;
  -webkit-margin-before: 1em;
  -webkit-margin-after: 1em;
  -webkit-margin-start: 0px;
  -webkit-margin-end: 0px;
  font-weight: bold;
}

.nuxt-content h4 {
  display: block;
  -webkit-margin-before: 1.33em;
  -webkit-margin-after: 1.33em;
  -webkit-margin-start: 0px;
  -webkit-margin-end: 0px;
  font-weight: bold;
}

.nuxt-content h5 {
  display: block;
  font-size: 0.83em;
  -webkit-margin-before: 1.67em;
  -webkit-margin-after: 1.67em;
  -webkit-margin-start: 0px;
  -webkit-margin-end: 0px;
  font-weight: bold;
}

.nuxt-content h6 {
  display: block;
  font-size: 0.67em;
  -webkit-margin-before: 2.33em;
  -webkit-margin-after: 2.33em;
  -webkit-margin-start: 0px;
  -webkit-margin-end: 0px;
  font-weight: bold;
}
</style>
