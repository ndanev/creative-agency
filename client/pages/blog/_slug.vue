<template>
  <div>
    <div class="hero">
      <div class="container">
        <div class="row">
          <div class="col-md-12 text-center">
            <h1 class="hero-title">
              Blog
            </h1>
          </div>
        </div>
      </div>
    </div>
    <section class="section">
      <div class="container">
        <div v-if="article" class="row justify-content-center">
          <div class="col-md-8">
            <nuxt-content :document="article" class="single-blog" />
          </div>
        </div>
        <div v-if="!article" class="row justify-content-center">
          <div class="col-md-8">
            Blog Not Found!
          </div>
        </div>
      </div>
    </section>
  </div>
</template>

<script>
export default {
  async asyncData ({ $content, params }) {
    const article = await $content('blog', params.slug).fetch()
    return { article }
  }
}
</script>

<style>
.single-blog img {
  max-width: 100%;
  height: auto;
  margin: 3rem 0;
}

.single-blog ul, .single-blog ol {
  padding-left: 1rem;
}
</style>
