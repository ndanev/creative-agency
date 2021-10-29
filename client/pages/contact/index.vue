<template>
  <div>
    <section class="section section-contact">
      <div class="container">
        <div class="row justify-content-center mb-5">
          <div class="col-md-6 text-center">
            <h1 class="section-title">
              <span>
                Contact
              </span>
            </h1>
            <p class="section-lead">
              If you have any question or you want to contact us, feel free to send us an email. We’re here to help you!
            </p>
          </div>
        </div>
        <div class="row">
          <div class="col-md-12">
            <form class="home-form" @submit.prevent="sendMessage">
              <div class="row">
                <div class="col-md-4">
                  <div class="form-group">
                    <label>Your Title</label>
                    <input type="text" class="form-control" placeholder="Enter Your Title">
                  </div>
                </div>
                <div class="col-md-4">
                  <div class="form-group">
                    <label>Your Name</label>
                    <input type="text" class="form-control" placeholder="Enter Your Name">
                  </div>
                </div>
                <div class="col-md-4">
                  <div class="form-group">
                    <label>Your Email</label>
                    <input type="text" class="form-control" placeholder="Enter Your Email">
                  </div>
                </div>
              </div>
              <div class="row">
                <div class="col-md-12">
                  <div class="form-colntrol">
                    <label>Your Message</label>
                    <textarea class="form-group w-100" rows="10" />
                  </div>
                </div>
              </div>
              <div class="row">
                <div class="col-md-12">
                  <button type="submit" class="button button-primary">
                    Send
                  </button>
                </div>
              </div>
            </form>
          </div>
        </div>
      </div>
    </section>
  </div>
</template>

<script>
export default {
  head () {
    return {
      title: 'Contact | Online Creative Agency',
      meta: [
        {
          hid: 'description',
          name: 'description',
          content: 'With a strong sense of aesthetic and an eye for pixel perfection, we pair with our clients to create the best versions of their design ideas. We offer elegant solutions and user experiences which enhance the online presence of a wide variety of businesses. Our team is ready for whatever it is your heart desires, willing to go the extra mile to create your perfect project.'
        }
      ]
    }
  },
  methods: {
    sendMessage () {
      alert('Functionality coming soon...')
    }
  }
}
</script>
