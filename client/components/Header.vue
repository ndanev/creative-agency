<template>
  <header class="header" :class="{header_fixed: scrollPosition > 0}">
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
        <ul v-show="desktopNav" class="header-list">
          <li v-for="(link, index) in headerLinks" :key="index" class="header-list-item">
            <nuxt-link class="header-list-link" :to="'/'+link.route">
              {{ link.name }}
            </nuxt-link>
          </li>
        </ul>
        <div v-show="mobile" class="menu-icon" @click="toggleMobileNav">
          <span>Menu</span>
          <i
            class="fas fa-bars"
            :class="{'fas fa-times': mobileNav}"
          />
        </div>
        <transition name="slide-fade" class="mobile-nav">
          <ul v-show="mobileNav" class="dropdown-nav">
            <li v-for="(link, index) in headerLinks" :key="index" class="header-list-item">
              <nuxt-link :to="'/'+link.route" @click.native="closeMenu()">
                {{ link.name }} <b-icon icon="arrow-right-short" />
              </nuxt-link>
            </li>
          </ul>
        </transition>
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
      scrollPosition: null,
      mobile: null,
      mobileNav: null,
      windowWidth: null,
      desktopNav: true,
      headerLinks: [
        {
          name: 'Home',
          route: ''
        },
        {
          name: 'About',
          route: 'about'
        },
        {
          name: 'Works',
          route: 'works'
        },
        {
          name: 'Process',
          route: 'process'
        },
        {
          name: 'Blogs',
          route: 'blogs'
        },
        {
          name: 'Contact',
          route: 'contact'
        },
        {
          name: 'Covid-19',
          route: 'covid'
        }
      ]
    }
  },
  beforeMount () {
    window.addEventListener('resize', this.checkScreen)
    this.checkScreen()
  },
  mounted () {
    window.addEventListener('scroll', this.updateScroll)
  },
  methods: {
    updateScroll () {
      this.scrollPosition = window.scrollY
    },
    toggleMobileNav () {
      this.mobileNav = !this.mobileNav
    },
    checkScreen () {
      this.windowWidth = window.innerWidth
      if (this.windowWidth <= 991) {
        this.mobile = true
        this.desktopNav = false
      } else {
        this.mobile = false
        this.mobileNav = false
        this.desktopNav = true
      }
    },
    closeMenu () {
      this.mobileNav = false
    }
  }
}
</script>

<style>
header {
  width: 100%;
  background-color: rgba(45, 25, 72, 1);
  transition: all .25s ease-in-out;
    border-bottom: 1px solid #705096;
}

.header_fixed {
  position: sticky;
  top: 30px;
  left: 0;
  z-index: 3;
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
}

.header-list {
  margin-bottom: 0;
}

.logo {
  z-index: 10;
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

.header-list-item:last-child {
  position: relative;
}

.header-list-item:last-child::before {
  content: 'New';
  position: absolute;
  top: -1rem;
  right: 1rem;
  background-color: #f33c7a;
  color: #fff;
  text-transform: uppercase;
  padding: 5px;
  border-radius: 4px;
  font-size: .4rem;
  font-weight: bold;
}

.header-list-link {
  padding: 1rem;
  text-transform: uppercase;
  font-weight: bold;
  color: #fff;
  position: relative;
  font-size: .9rem;
  transition: all .25s;
}

.header-list-link.nuxt-link-exact-active.nuxt-link-active:before {
  position: absolute;
  content: "";
  left: 1rem;
  bottom: 10px;
  width: 30%;
  height: 4px;
  background-color: #f33c7a;
  z-index: 1;
  margin: 0 auto;
  transition: all .25s ease-in;
}

.header-list-link:hover {
  color: #d8c9f5;
}

.header-list-link:hover::before {
  position: absolute;
  content: "";
  left: 1rem;
  bottom: 10px;
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

.menu-icon {
  color: #fff;
  display: flex;
  align-items: center;
  justify-content: center;
  cursor: pointer;
  font-size: 1.6rem;
}

.menu-icon span {
  font-size: 1.2rem;
  margin-right: .5rem;
}

.dropdown-nav {
  display: flex;
  flex-direction: column;
  justify-content: center;
  position: fixed;
  left: 0;
  top: 0;
  z-index: 9;
  width: 100%;
  max-width: 275px;
  height: 100%;
  background-color: #1b0c30;
  transition: all .25s ease-in-out;
}

.dropdown-nav .header-list-item {
  border-bottom: 1px solid #705096;
}

.dropdown-nav .header-list-item:first-child {
    border-top: 1px solid #705096;
}

.dropdown-nav a {
  color: #fff;
  padding: 15px 15px 15px 30px;
  display: block;
  text-transform: uppercase;
  font-weight: bold;
  transition: all .25s ease-in-out;
}

.dropdown-nav a:hover, .dropdown-nav a:active, .dropdown-nav a:focus {
  color: #f33c7a;
}

.slide-fade-enter-active {
  transition: all .3s ease;
}
.slide-fade-leave-active {
  transition: all .1s cubic-bezier(1.0, 0.5, 0.8, 1.0);
}
.slide-fade-enter, .slide-fade-leave-to {
  transform: translateX(-10px);
  opacity: 0;
}

@media (max-width: 991px) {
  .header-list-item:last-child::before {
    top: 50%;
    transform: translateY(-50%);
  }
}

@media (max-width: 767px) {
  .logo-link {
    padding: 1rem 0;
  }
}
</style>
