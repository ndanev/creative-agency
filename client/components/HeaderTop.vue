<template>
  <div class="header-top" :class="{header_top_fixed: scrollPosition > 0}">
    <div class="container-fluid">
      <div class="d-flex align-items-center justify-content-between">
        <h1>
          Web Design & <span>Development</span>
        </h1>
        <div class="phone-number">
          <i class="fas fa-phone-alt" />
          <a href="tel:+14373283418">
            (437) 328-3418
          </a>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'HeaderTop',
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
.header-top {
    padding: 0 1rem;
    background-color: rgba(27, 12, 48, 1);
    width: 100%;
    height: 30px;
    display: flex;
    align-items: center;
    justify-content: space-between;
    transition: all .25s ease-in-out;
}

.header_top_fixed {
    position: sticky;
    top: 0;
    left: 0;
    z-index: 3;
}

.header-top h1 span {
  color: #f33c7a;
}

.header-top h1 {
    font-size: 1rem;
    margin-bottom: 0;
    font-weight: bold;
    color: #fff;
}

.header-top i {
    color: #fff;
}

.header-top a {
    color: #fff;
    font-weight: bold;
    transition: all .25s;
}

.phone-number a:hover {
  color: #f33c7a;
}

@media (max-width: 767px) {
  .header-top {
    padding: 0;
  }
}

@media (max-width: 450px) {
  .header-top a {
    font-size: .7rem;
  }

  .header-top i {
    font-size: .7rem;
  }

  .header-top h1 {
    font-size: .7rem;
  }
}
</style>
