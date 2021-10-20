<template>
  <div class="home">
    <div class="hero-home">
      <div class="container h-100">
        <div class="row h-100">
          <div class="col-md-7 d-flex justify-content-center flex-column">
            <h1 class="hero-title">
              Online <br> Creative
              <span>Agency</span>
            </h1>
            <p class="hero-lead mb-5">
              Lorem ipsum dolor sit amet consectetur adipisicing elit. Cum explicabo deleniti labore eius dolorum facilis minima itaque nihil, illo natus?
            </p>
            <div>
              <router-link class="button button-primary" to="/contact">
                Contact Us
              </router-link>
            </div>
          </div>
          <div class="col-md-5"></div>
        </div>
      </div>
    </div>
    <section class="section section-about">
      <div class="container">
        <div class="row">
          <div class="col-md-12 text-center">
            <h1 class="section-title">
              About Us
            </h1>
          </div>
        </div>
        <div class="row">
          <div class="col-md-6 d-flex flex-column justify-content-center">
            <h2 class="section-subtitle">
              We are
              <br>
              <span>Creative Agnecy</span>
            </h2>
            <p class="section-lead">
              Lorem ipsum dolor sit amet consectetur adipisicing elit. Praesentium, fuga necessitatibus voluptate, consequatur aliquam harum nostrum, vitae dolore ipsa placeat tempora nesciunt ab porro. Ipsum, veritatis earum voluptatibus dolores animi molestiae, itaque architecto delectus alias accusantium quisquam ratione, quis minima!
            </p>
          </div>
          <div class="col-md-6 text-center">
            <img src="@/assets/images/home-about.png" class="img-fluid" alt>
          </div>
        </div>
      </div>
    </section>
    <section class="section section-skills">
      <div class="container">
        <div class="row justify-content-center mb-5">
          <div class="col-md-6 text-center">
            <h1 class="section-title">
              Our Skills
            </h1>
            <p class="section-lead">
              Lorem ipsum dolor sit, amet consectetur adipisicing elit. Perspiciatis facilis aut iste tenetur aliquam enim cupiditate dolore consequatur laborum labore assumenda repellat tempore, nam voluptatibus.
            </p>
          </div>
        </div>
        <div class="row">
          <div v-for="(skill, index) in skills" :key="index" class="col-md-3">
            <div class="skill-circle">
              <div class="skill-circle-inner">
                <div class="skill-circle-inner-progress">
                  {{ skill.num }}
                </div>
              </div>
              {{ skill.title }}
            </div>
          </div>
        </div>
      </div>
    </section>
    <section class="section section-works">
      <div class="container-fluid">
        <div class="row justify-content-center mb-5">
          <div class="col-md-4 text-center">
            <h1 class="section-title">
              Our Works
            </h1>
            <p class="section-lead">
              Lorem ipsum dolor sit, amet consectetur adipisicing elit. Sit fugit quasi laborum ut aut quisquam rem ipsum consectetur deserunt in!
            </p>
          </div>
        </div>
        <div class="row">
          <div class="col-md-3">
            <div class="work-card">
              <img src="@/assets/images/work-1.png" class="img-fluid" alt>
            </div>
          </div>
          <div class="col-md-3">
            <div class="work-card">
              <img src="@/assets/images/work-2.png" class="img-fluid" alt>
            </div>t>
          </div>
          <div class="col-md-3">
            <div class="work-card">
              <img src="@/assets/images/work-3.png" class="img-fluid" alt>
            </div>
          </div>
          <div class="col-md-3">
            <div class="work-card">
              <img src="@/assets/images/work-4.png" class="img-fluid" alt>
            </div>
          </div>
          <div class="col-md-3">
            <div class="work-card">
              <img src="@/assets/images/work-5.png" class="img-fluid" alt>
            </div>
          </div>
          <div class="col-md-3">
            <div class="work-card">
              <img src="@/assets/images/work-6.png" class="img-fluid" alt>
            </div>
          </div>
          <div class="col-md-3">
            <div class="work-card">
              <img src="@/assets/images/work-7.png" class="img-fluid" alt>
            </div>
          </div>
          <div class="col-md-3">
            <div class="work-card">
              <img src="@/assets/images/work-8.png" class="img-fluid" alt>
            </div>
          </div>
        </div>
      </div>
    </section>
  </div>
</template>

<script>
export default {
  name: 'Home',
  components: {},
  data () {
    return {
      skills: [
        {
          title: '7 Years on Business',
          num: '7'
        },
        {
          title: 'Top 10 on web',
          num: '10'
        },
        {
          title: 'Completed Projects',
          num: '250'
        },
        {
          title: 'Happy Clients',
          num: '98%'
        }
      ]
    }
  }
}
</script>

<style>
.hero-home {
  background-image: url("../assets/images/hero-home.png");
  background-repeat: no-repeat;
  background-size: cover;
  height: 100vh;
  width: 100%;
}

.hero-title {
  color: #ffffff;
  font-size: 4rem;
  font-weight: bold;
  text-transform: uppercase;
}

.hero-title span {
  color: #f33c7a;
}

.hero-lead {
  color: #ffffff;
  font-size: 1.6rem;
}

.button {
  padding: 20px 50px;
  font-size: 1rem;
  font-weight: bold;
  text-transform: uppercase;
}

.button-primary {
  background-color: #f33c7a;
  color: #ffffff;
}

.button-primary:hover {
  color: #ffffff;
}

.section-about {
  background-color: #2d1948;
}

.section-skills {
  background-color: #1b0c30;
}

.section-skills .section-title {
  margin-bottom: 2rem;
}

.skill-circle {
  text-align: center;
  color: #fff;
  font-size: 1.4rem;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
}

.skill-circle-inner {
  width: 200px;
  height: 200px;
  border-radius: 50%;
  margin-bottom: 1rem;
}

.skill-circle-inner-progress {
  width: 100%;
  height: 100%;
  border-radius: 50%;
  border: 5px solid #fff;
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: 3rem;
  color: #fff;
}

.section-works {
  background-color: #2d1948;
}

.section-works .section-title {
  margin-bottom: 2rem;
}

.work-card {
  margin-bottom: 1rem;
}
</style>
