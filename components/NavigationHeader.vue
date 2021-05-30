<template>
  <nav class="navbar container" role="navigation" aria-label="main navigation">
    <div class="navbar-brand">
      <NuxtLink to="/" class="navbar-item has-text-black">
        <i class="snes-jp-logo navbar-item" />
      </NuxtLink>
      <a role="button" class="navbar-burger" aria-label="menu" aria-expanded="false" data-target="burgerItems">
        <span aria-hidden="true" />
        <span aria-hidden="true" />
        <span aria-hidden="true" />
      </a>
    </div>
    <div id="burgerItems" class="navbar-menu">
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
        <div class="navbar-item">
          <i class="nes-icon twitter" />
        </div>
        <div class="navbar-item">
          <i class="nes-icon github" />
        </div>
      </div>
    </div>
  </nav>
</template>

<script>
export default {
  name: 'NavigationHeader'
}
</script>
