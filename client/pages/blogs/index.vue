<template>
  <div class="blogs">
    <div class="hero">
      <div class="container">
        <div class="row">
          <div class="col-md-12 text-center">
            <h1 class="hero-title">
              Blogs
            </h1>
          </div>
        </div>
      </div>
    </div>
    <section class="section">
      <div class="row">
        <div class="col-md-12 text-center">
          <h2 class="section-title">
            Read our <span>blogs</span>
          </h2>
        </div>
      </div>
      <div class="container">
        <div class="row justify-content-center">
          <div v-for="(article, index) in articles" :key="index" class="col-md-8 mb-3">
            <nuxt-link :to="{ name: 'blog-slug', params:{slug: article.slug}}" class="d-block blog-card mb-3 mb-md-0">
              <img :src="require(`@/assets/images/${article.image}`)" class="img-fluid" alt>
              <div class="details">
                <h3>
                  {{ article.title }}
                </h3>
                <p>
                  {{ article.desc.substring(0,120) }}...
                </p>
              </div>
            </nuxt-link>
          </div>
        </div>
      </div>
    </section>
  </div>
</template>

<script>
export default {
  async asyncData ({ $content, params }) {
    const articles = await $content('blog', params.slug).only(['title', 'desc', 'image', 'slug']).sortBy('createdAt', 'asc').fetch()
    return { articles }
  }
}
</script>

<style>
.blogs .section-title {
  color: #212529;
}

.blogs .section-title span {
  color: #f33c7a;
}

.blogs .section-title span:before {
  display: none;
}
</style>
