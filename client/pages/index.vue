<template>
  <div class="home">
    <div class="hero-home">
      <div class="container h-100">
        <div class="row h-100">
          <div class="col-md-7 offset d-flex justify-content-center flex-column">
            <h1 class="hero-title">
              Online <br> Creative
              <span>Agency</span>
            </h1>
            <p class="hero-lead mb-5">
              Lorem ipsum dolor sit amet consectetur adipisicing elit. Cum explicabo deleniti labore eius dolorum facilis minima itaque nihil, illo natus?
            </p>
            <div>
              <nuxt-link class="button button-primary" to="/contact">
                Contact Us
              </nuxt-link>
            </div>
          </div>
        </div>
      </div>
    </div>
    <section class="section section-about">
      <div class="container">
        <div class="row">
          <div class="col-md-12 text-center">
            <h1 class="section-title">
              <span>
                About Us
              </span>
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
              <span>
                Our Skills
              </span>
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
              {{ skill.skillTitle }}
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
              <span>
                Our Works
              </span>
            </h1>
            <p class="section-lead">
              Lorem ipsum dolor sit, amet consectetur adipisicing elit. Sit fugit quasi laborum ut aut quisquam rem ipsum consectetur deserunt in!
            </p>
          </div>
        </div>
        <div class="row justify-content-center">
          <div v-for="work in works" :key="work.id" class="column">
            <WorkCard :title="work.workTitle" :image="work.img" />
          </div>
        </div>
      </div>
    </section>
    <section id="process" class="section section-process">
      <div class="container">
        <div class="row justify-content-center mb-5">
          <div class="col-md-6 text-center">
            <h1 class="section-title">
              <span>
                Our Work Process
              </span>
            </h1>
            <p class="section-lead">
              Lorem ipsum dolor sit, amet consectetur adipisicing elit. Sit fugit quasi laborum ut aut quisquam rem ipsum consectetur deserunt in!
            </p>
          </div>
        </div>
        <div class="row">
          <div v-for="(process, index) in workProcess" :key="index" class="col-md-4">
            <ProcessCard :processTitle="process.processTitle" :processDesc="process.processDesc" />
          </div>
        </div>
      </div>
    </section>
    <div class="section section-blog">
      <div class="container">
        <div class="row justify-content-center">
          <div class="col-md-6 text-center">
            <h1 class="section-title">
              <span>
                Latest Posts
              </span>
            </h1>
          </div>
        </div>
        <div class="row">
          <div v-for="(article, index) in articles" :key="index" class="col-md-4">
            <nuxt-link :to="{ name: 'blog-slug', params:{slug: article.slug}}" class="d-block blog-card">
              <img :src="require(`@/assets/images/${article.image}`)" class="img-fluid">
              <div class="details">
                <h3>
                  {{ article.title }}
                </h3>
                <p>
                  {{ article.desc }}
                </p>
              </div>
            </nuxt-link>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  async asyncData ({ $content, params }) {
    const articles = await $content('blog', params.slug).only(['title', 'desc', 'image', 'slug']).sortBy('createdAt', 'asc').fetch()
    return { articles }
  },
  data () {
    return {
      skills: [
        {
          skillTitle: '7 Years on Business',
          num: '7'
        },
        {
          skillTitle: 'Top 10 on web',
          num: '10'
        },
        {
          skillTitle: 'Completed Projects',
          num: '250'
        },
        {
          skillTitle: 'Happy Clients',
          num: '98%'
        }
      ],
      works: [
        {
          id: 1,
          workTitle: 'Project 1',
          project_gh_link: '',
          img: require('@/assets/images/work-1.png')
        },
        {
          id: 2,
          workTitle: 'Project 2',
          project_gh_link: '',
          img: require('@/assets/images/work-2.png')
        },
        {
          id: 3,
          workTitle: 'Project 3',
          project_gh_link: '',
          img: require('@/assets/images/work-3.png')
        },
        {
          id: 4,
          workTitle: 'Project 4',
          project_gh_link: '',
          img: require('@/assets/images/work-4.png')
        },
        {
          id: 5,
          workTitle: 'Project 5',
          project_gh_link: '',
          img: require('@/assets/images/work-5.png')
        },
        {
          id: 6,
          workTitle: 'Project 6',
          project_gh_link: '',
          img: require('@/assets/images/work-6.png')
        },
        {
          id: 7,
          workTitle: 'Project 7',
          project_gh_link: '',
          img: require('@/assets/images/work-7.png')
        },
        {
          id: 8,
          workTitle: 'Project 8',
          project_gh_link: '',
          img: require('@/assets/images/work-8.png')
        }
      ],
      workProcess: [
        {
          processTitle: 'Planning',
          processDesc: 'A project plan is a series of formal documents that define the execution and control stages of a project. The plan includes considerations for risk management, resource management and communications, while also addressing scope, cost and schedule baselines.'
        },
        {
          processTitle: 'Designing',
          processDesc: 'Web design encompasses many different skills and disciplines in the production and maintenance of websites. The different areas of web design include web graphic design; user interface design (UI design); authoring, including standardised code and proprietary software; user experience design (UX design); and search engine optimization.'
        },
        {
          processTitle: 'Development',
          processDesc: 'Web development is the work involved in developing a website for the Internet (World Wide Web) or an intranet (a private network). Web development can range from developing a simple single static page of plain text to complex web applications, electronic businesses, and social network services.'
        },
        {
          processTitle: 'Testing',
          processDesc: 'Web testing is software testing that focuses on web applications. Complete testing of a web-based system before going live can help address issues before the system is revealed to the public. Issues may include the security of the web application, the basic functionality of the site, its accessibility to handicapped users and fully able users, its ability to adapt to the multitude of desktops, devices, and operating systems, as well as readiness for expected traffic and number of users and the ability to survive a massive spike in user traffic, both of which are related to load testing.'
        },
        {
          processTitle: 'Deployment',
          processDesc: 'Software deployment is all of the activities that make a software system available for use. The general deployment process consists of several interrelated activities with possible transitions between them. These activities can occur at the producer side or at the consumer side or both. Because every software system is unique, the precise processes or procedures within each activity can hardly be defined. Therefore, "deployment" should be interpreted as a general process that has to be customized according to specific requirements or characteristics.'
        },
        {
          processTitle: 'Maintenance',
          processDesc: 'Maintenance in software engineering is the modification of a software product after delivery to correct faults, to improve performance or other attributes. A common perception of maintenance is that it merely involves fixing defects. The key software maintenance issues are both managerial and technical. Key management issues are: alignment with customer priorities, staffing, which organization does maintenance, estimating costs. Key technical issues are: limited understanding, impact analysis, testing, maintainability measurement.'
        }
      ]
    }
  }
}
</script>

<style>
.hero-home {
  background-image: url("@/assets/images/hero-home.png");
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

.column {
  padding: 5px;
}

.section-process {
  background-image: url("@/assets/images/work-process-bg.png");
  background-repeat: no-repeat;
  background-position: center;
  background-size: cover;
}

.section-process .section-title {
  margin-bottom: 2rem;
}

.section-blog {
  background-color: #2d1948;
}

.blog-card .details {
  background: #fff;
  color: #1b0c30;
  padding: 1rem;
}
.blog-card .details h3 {
  font-weight: bold;
  font-size: 1.2rem;
  text-transform: uppercase;
}

.blog-card img {
  height: 150px;
  width: 100%;
  object-fit: cover;
}

@media (max-width: 991px) {
  .hero-home {
    background-position: 75%;
  }
}
</style>
