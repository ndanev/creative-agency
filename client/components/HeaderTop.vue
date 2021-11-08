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
    display: -webkit-box;
    display: -ms-flexbox;
    display: flex;
    -webkit-box-align: center;
        -ms-flex-align: center;
            align-items: center;
    -webkit-box-pack: justify;
        -ms-flex-pack: justify;
            justify-content: space-between;
    -webkit-transition: all .25s ease-in-out;
    -o-transition: all .25s ease-in-out;
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
    -webkit-transition: all .25s;
    -o-transition: all .25s;
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
