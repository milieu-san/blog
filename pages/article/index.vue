<template>
  <div class="container is-fluid">
    <div class="hero">
      <div class="hero-body">
        <div class="container is-max-desktop">
          <div class="columns is-left">
            <div class="column">
              <p class="title">
                Blogs
              </p>
              <p>
                きっと きが むいたら こうしん するだろう
              </p>
            </div>
          </div>
        </div>
      </div>
    </div>
    <div class="container is-max-desktop">
      <div class="columns">
        <div class="column is-three-fifths">
          <div class="nes-field is-flex">
            <input id="search_box" v-model="query" type="text" class="nes-input" @keypress.enter="fetchArticles">
            <span type="button" class="nes-btn is-primary" @click.prevent="fetchArticles">
              Search
            </span>
          </div>
        </div>
      </div>
      <div v-if="isLoading">
        <p>しょうしょう おまちください。</p>
      </div>
      <div v-else-if="articles.length > 0" class="columns">
        <div class="column">
          <div
            v-for="article in articles"
            :key="article.id"
            class="nes-container with-title is-rounded mt-5 pb-0"
          >
            <NuxtLink :to="`/article/${article.id}`" class="title">
              {{ article.title }}
            </NuxtLink>
            <div class="columns">
              <NuxtLink :to="`/article/${article.id}`" class="column is-three-quarters has-text-black">
                {{ article.description }}
              </NuxtLink>
              <div class="column is-one-quarter has-text-centered">
                <i class="nes-jp-logo" />
              </div>
            </div>
            <div class="columns">
              <div class="column is-one-quarter py-0">
                <span>{{ article.createdAt | dateStr }}</span>
              </div>
              <div class="column py-0">
                <span class="ml-2">
                  {{ article.tags }}
                </span>
              </div>
            </div>
          </div>
        </div>
      </div>
      <div v-else>
        <p>きじが ありません。</p>
      </div>
    </div>
  </div>
</template>

<script>
import moment from 'moment'

export default {
  filters: {
    dateStr (date) {
      return moment(date).format('YYYY/MM/DD HH:mm')
    }
  },
  data () {
    return {
      articles: [],
      query: '',
      isLoading: false
    }
  },
  created () {
    this.fetchArticles()
  },
  methods: {
    async fetchArticles () {
      this.isLoading = true
      this.articles = await this.$content('articles')
        .where({ public: true })
        .sortBy('createdAt', 'desc')
        .search(this.query)
        .fetch()
      this.isLoading = false
    }
  }
}
</script>
