<template>
  <div>
    <div class="hero">
      <div class="container">
        <div class="row justify-content-center">
          <div class="col-md-8">
            <h1 class="hero-title">
              {{ article.title }}
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
      </div>
    </section>
  </div>
</template>

<script>
export default {
  async asyncData ({ $content, params }) {
    const article = await $content('blog', params.slug).fetch()
    return { article }
  },
  head () {
    return {
      title: 'Blog | Online Creative Agency',
      meta: [
        {
          hid: 'description',
          name: 'description',
          content: 'Web development is the work involved in developing a website for the Internet (World Wide Web) or an intranet (a private network). Web development can range from developing a simple single static page of plain text to complex web applications, electronic businesses, and social network services.'
        }
      ]
    }
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
