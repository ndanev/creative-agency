<template>
  <div class="about">
    <div class="hero">
      <div class="container">
        <div class="row">
          <div class="col-md-12 text-center">
            <h1 class="hero-title">
              {{ aboutContact.heroTitle }}
            </h1>
          </div>
        </div>
      </div>
    </div>
    <section class="section">
      <div class="container">
        <div class="row justify-content-center">
          <div class="col-md-8 text-center">
            <h2 class="section-title">
              {{ aboutContact.sectionTitle }}
            </h2>
            <p class="section-lead">
              {{ aboutContact.sectionSubtitle }}
            </p>
            <img
              src="@/assets/images/about-page.jpg"
              class="img-fluid"
              width="730"
              height="310"
              :alt="aboutContact.sectionTitle"
              :title="aboutContact.sectionTitle"
            >
          </div>
        </div>
      </div>
    </section>
  </div>
</template>

<script>
export default {
  data () {
    return {
      aboutContact: {
        heroTitle: 'About',
        sectionTitle: 'We are Creative Agnecy',
        sectionSubtitle: 'With a strong sense of aesthetic and an eye for pixel perfection, we pair with our clients to create the best versions of their design ideas. We offer elegant solutions and user experiences which enhance the online presence of a wide variety of businesses. Our team is ready for whatever it is your heart desires, willing to go the extra mile to create your perfect project.'
      }
    }
  },
  head () {
    return {
      title: 'About | Online Creative Agency',
      meta: [
        {
          hid: 'description',
          name: 'description',
          content: 'With a strong sense of aesthetic and an eye for pixel perfection, we pair with our clients to create the best versions of their design ideas. We offer elegant solutions and user experiences which enhance the online presence of a wide variety of businesses. Our team is ready for whatever it is your heart desires, willing to go the extra mile to create your perfect project.'
        }
      ]
    }
  }
}
</script>

<style>
  .about .section-title {
    color: #212529;
    margin-bottom: 1rem;
  }
  .about .section-lead {
    color: #212529;
    margin-bottom: 3rem;
  }
</style>
