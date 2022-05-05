<template>
  <nav class="navbar container" role="navigation" aria-label="main navigation">
    <div class="navbar-brand">
      <NuxtLink to="/" class="navbar-item has-text-black">
        <img src="~/assets/images/miball0202-1.png" alt="logo-image" width="30">
      </NuxtLink>
      <a
        role="button"
        class="navbar-burger"
        aria-label="menu"
        aria-expanded="false"
        data-target="burgerItems"
        @click.prevent="isOpen = !isOpen"
      >
        <span aria-hidden="true" class="hidden-item" />
        <span aria-hidden="true" class="hidden-item" />
        <span aria-hidden="true" class="hidden-item" />
      </a>
    </div>
    <div id="burgerItems" class="navbar-menu" :class="{'is-active': isOpen}">
      <div class="navbar-start">
        <NuxtLink to="/" class="navbar-item has-text-dark">
          Home
        </NuxtLink>

        <NuxtLink to="/article" class="navbar-item has-text-dark">
          Blog
        </NuxtLink>

        <NuxtLink to="/about" class="navbar-item has-text-dark">
          About
        </NuxtLink>
      </div>

      <div class="navbar-end">
        <a href="https://twitter.com/miball0202" target="_blank" rel="noopener" class="navbar-item">
          <i class="nes-icon twitter" />
        </a>
        <a href="https://github.com/miball0202" target="_blank" rel="noopener" class="navbar-item">
          <i class="nes-icon github" />
        </a>
      </div>
    </div>
  </nav>
</template>

<script>
export default {
  name: 'TheNavigationHeader',
  data () {
    return {
      isOpen: false
    }
  }
}
</script>

<style scoped>
.hidden-item {
  height: 2px;
}
</style>
