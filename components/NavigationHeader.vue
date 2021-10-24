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
        <span aria-hidden="true" style="height: 2px" />
        <span aria-hidden="true" style="height: 2px" />
        <span aria-hidden="true" style="height: 2px" />
      </a>
    </div>
    <div id="burgerItems" class="navbar-menu" :class="{'is-active': isOpen}">
      <div class="navbar-start">
        <NuxtLink to="/" class="navbar-item has-text-dark">
          Home
        </NuxtLink>

        <NuxtLink to="/blogs" class="navbar-item has-text-dark">
          Blogs
        </NuxtLink>

        <div class="navbar-item has-dropdown is-hoverable has-text-dark">
          <a class="navbar-link">
            Works
          </a>

          <div class="navbar-dropdown">
            <NuxtLink to="/about" class="navbar-item has-text-dark">
              About
            </NuxtLink>
            <hr class="navbar-divider">
            <a class="navbar-item">
              Development
            </a>
            <a class="navbar-item">
              Scenario
            </a>
            <a class="navbar-item">
              Music
            </a>
            <hr class="navbar-divider">
            <a class="navbar-item">
              Contact
            </a>
          </div>
        </div>
      </div>

      <div class="navbar-end">
        <a href="https://twitter.com/SeMiyabi" target="_blank" rel="noopener" class="navbar-item">
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
  name: 'NavigationHeader',
  data () {
    return {
      isOpen: false
    }
  }
}
</script>
