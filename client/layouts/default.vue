<template>
  <div>
    <Header />
    <Nuxt />
    <Footer />
  </div>
</template>

<script>
export default {}
</script>

<style>
* {
  padding: 0;
  margin: 0;
  font-family: "Lato", sans-serif;
}

.app {
  position: relative;
}

.section {
  padding: 120px 0;
}

.section-title {
  color: #fff;
  font-size: 2.8rem;
  text-transform: uppercase;
  font-weight: bold;
  margin-bottom: 5rem;
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
</style>
