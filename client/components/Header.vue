<template>
  <header class="header" :class="{header_bg: scrollPosition > 200}">
    <div class="container-fluid">
      <nav>
        <div class="logo">
          <nuxt-link class="logo-link" to="/">
            <div class="logo-prefix">
              online
            </div>Creative
            <span>Agency</span>
          </nuxt-link>
        </div>
        <ul class="header-list">
          <li class="header-list-item">
            <nuxt-link class="header-list-link" to="/">
              Home
            </nuxt-link>
          </li>
          <li class="header-list-item">
            <nuxt-link class="header-list-link" to="/about">
              About
            </nuxt-link>
          </li>
          <li class="header-list-item">
            <nuxt-link class="header-list-link" to="/work">
              Work
            </nuxt-link>
          </li>
          <li class="header-list-item">
            <nuxt-link class="header-list-link" to="#process">
              Process
            </nuxt-link>
          </li>
          <li class="header-list-item">
            <nuxt-link class="header-list-link" to="/services">
              Services
            </nuxt-link>
          </li>
          <li class="header-list-item">
            <nuxt-link class="header-list-link" to="/testimonials">
              Testimonials
            </nuxt-link>
          </li>
          <li class="header-list-item">
            <nuxt-link class="header-list-link" to="/contact">
              Contact
            </nuxt-link>
          </li>
        </ul>
      </nav>
    </div>
  </header>
</template>

<script>
export default {
  name: 'Header',
  components: {},
  data () {
    return {
      scrollPosition: null
    }
  },
  mounted () {
    window.addEventListener('scroll', this.updateScroll)
  },
  methods: {
    updateScroll () {
      this.scrollPosition = window.scrollY
    }
  }
}
</script>

<style>
header {
  position: fixed;
  top: 30px;
  left: 0;
  width: 100%;
  z-index: 3;
}

.header_bg {
  /* background-color: #2d1948; */
  background-color: rgba(45, 25, 72, 1);
}

a {
  text-decoration: none !important;
}

ul {
  list-style-type: none;
  display: flex;
  padding: 0;
  margin: 0;
}

header nav {
  display: flex;
  align-items: center;
  justify-content: space-between;
  border-bottom: 1px solid #705096;
}

.header-list {
  margin-bottom: 0;
}

.logo-link {
  font-size: 1rem;
  font-weight: bold;
  text-transform: uppercase;
  padding: 1rem;
  color: #fff;
  display: flex;
  flex-direction: column;
  align-items: center;
}

.logo-link:hover {
  color: #fff;
}

.logo-link span {
  color: #f33c7a;
  font-size: 1.4rem;
  margin-top: -0.4rem;
  line-height: 1.6rem;
}

.logo-link .logo-prefix {
  font-size: 0.6rem;
  font-weight: 100;
  margin-left: 40px;
  margin-bottom: -5px;
    transition: all .25s ease-in-out;
}

.logo-link:hover > .logo-prefix {
  margin-left: -40px;
}

.header-list-link {
  padding: 1rem;
  text-transform: uppercase;
  font-weight: bold;
  color: #fff;
  position: relative;
  font-size: .9rem;
}

.header-list-link:hover {
  color: #d8c9f5;
}

.header-list-link:hover::before {
  position: absolute;
  content: "";
  left: 1rem;
  bottom: 0;
  width: 50%;
  height: 4px;
  background-color: #f33c7a;
  z-index: 1;
  margin: 0 auto;
}

.header-list-link.router-link-exact-active.router-link-active::before {
  position: absolute;
  content: "";
  left: 1rem;
  bottom: 0;
  width: 50%;
  height: 4px;
  background-color: #f33c7a;
  z-index: 1;
  margin: 0 auto;
}
</style>
