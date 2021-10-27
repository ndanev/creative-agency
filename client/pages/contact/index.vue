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
              Lorem ipsum dolor sit, amet consectetur adipisicing elit. Sit fugit quasi laborum ut aut quisquam rem ipsum consectetur deserunt in!
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
                    <textarea id="" class="form-group w-100" name="" rows="10" />
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
  methods: {
    sendMessage () {
      alert('Functionality coming soon...')
    }
  }
}
</script>
