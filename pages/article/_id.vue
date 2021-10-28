<template>
  <div class="container blog-content">
    <div class="hero">
      <div class="hero-body pb-0">
        <div class="container is-max-desktop">
          <p>公開日: {{ article.publishedAt }}</p>
          <p class="title">
            {{ article.title }}
          </p>
          <p>
            <span class="icon">
              <i class="fas fa-tags" />
            </span>
            {{ article.tags }}
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

a {
  text-decoration: none;
}

.icon-link::before {
  font-size: medium;
  font-weight: 900;
  content: '\f0c1';
  padding-right: 20px;
  color: lightskyblue;
}

.blog-content * {
  font-family: "Source Code Pro", Monaco, monospace, "Font Awesome 5 Free";
}

.nuxt-content ul {
  margin: 1em 0;
  padding-left: 20px;
  list-style-type: disc;
}

.nuxt-content ol {
  margin: 1em 0;
  padding-left: 20px;
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
  border-bottom: 1px solid #ddd;
  padding-bottom: 0.1em;
}

.nuxt-content h2 {
  display: block;
  font-size: 1.5em;
  -webkit-margin-before: 0.83em;
  -webkit-margin-after: 0.83em;
  -webkit-margin-start: 0px;
  -webkit-margin-end: 0px;
  font-weight: bold;
  border-bottom: 1px solid #ddd;
  padding-bottom: 0.1em;
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
