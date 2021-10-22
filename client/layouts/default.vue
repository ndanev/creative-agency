<template>
  <main class="main">
    <HeaderTop />
    <Header />
    <Nuxt />
    <EmailMe />
    <Footer />
  </main>
</template>

<script>
export default {
}
</script>

<style>
* {
  padding: 0;
  margin: 0;
  font-family: "Lato", sans-serif;
}

body {
  overflow-x: hidden;
}

html {
  scroll-behavior: smooth;
}

.main {
  position: relative;
}

.app {
  position: relative;
}

.section {
  padding: 80px 0;
}

.section-title {
  color: #fff;
  font-size: 2rem;
  text-transform: uppercase;
  font-weight: bold;
  margin-bottom: 5rem;
}

.section-title span {
  position: relative;
  z-index: 1;
}

.section-title span:before {
  content: '';
  position: absolute;
  bottom: 5px;
  left: 0;
  width: 100%;
  height: 10px;
  border-radius: 4px;
  background-color: #f33c7a;
  z-index: -1;

}

.section-subtitle {
  color: #fff;
  font-size: 2.4rem;
}

.section-subtitle span {
  color: #f33c7a;
  text-transform: uppercase;
  font-weight: bold;
}

.section-lead {
  color: #fff;
  font-size: 1.2rem;
}

@media (max-width: 767px) {
  .section {
    padding: 40px 0;
  }
}
</style>
