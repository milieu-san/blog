<template>
  <div>
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
          <a class="navbar-item">
            Home
          </a>

          <a class="navbar-item">
            Blogs
          </a>

          <div class="navbar-item has-dropdown is-hoverable">
            <a class="navbar-link">
              Works
            </a>

            <div class="navbar-dropdown">
              <a class="navbar-item">
                About
              </a>
              <hr class="navbar-divider">
              <a class="navbar-item">
                Code
              </a>
              <a class="navbar-item">
                Script
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

    <div class="container">
      <div class="section">
        <div class="hero is-fullheight">
          <div class="hero-body">
            <div class="container">
              <div class="columns is-full">
                <div class="column has-text-centered">
                  <h1 class="title">
                    これが ぼくだ
                  </h1>
                  <h2 class="subtitle mt-1">
                    とくべつな ことは ない
                  </h2>
                  <h2 class="subtitle">
                    ここには ありのまま かく
                  </h2>
                </div>
                <div class="column has-text-centered">
                  <img src="~/assets/images/20210530183248828.gif" alt="" />
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {}
</script>
