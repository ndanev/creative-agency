<template>
  <div class="home">
    <div class="hero-home">
      <div class="container h-100">
        <div class="row h-100">
          <div class="col-md-7 offset d-flex  justify-content-center flex-column">
            <h1 class="hero-home-title">
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
          <div class="col-md-12 text-left text-md-center">
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
          <div v-for="(skill, index) in skills" :key="index" class="col-md-4">
            <SkillCard :title="skill.title" :image="skill.image" :desc="skill.desc" />
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
            <WorkCard :title="work.workTitle" :image="work.img" :link="work.gitLink" :website="work.website" />
          </div>
        </div>
      </div>
    </section>
    <section class="section section-process">
      <div class="container">
        <div class="row justify-content-center mb-5">
          <div class="col-md-6 text-center">
            <h1 class="section-title">
              <span>
                Work Process
              </span>
            </h1>
            <p class="section-lead">
              Lorem ipsum dolor sit, amet consectetur adipisicing elit. Sit fugit quasi laborum ut aut quisquam rem ipsum consectetur deserunt in!
            </p>
          </div>
        </div>
        <div class="row">
          <div v-for="(process, index) in workProcess" :key="index" class="col-12 col-sm-6 col-md-4">
            <ProcessCard :id="process.id" :title="process.title" :desc="process.desc" />
          </div>
        </div>
      </div>
    </section>
    <section class="section section-blog">
      <div class="container-fluid">
        <div class="row justify-content-center">
          <div class="col-md-6 text-center">
            <h1 class="section-title">
              <span>
                Latest Blogs
              </span>
            </h1>
          </div>
        </div>
        <div class="row">
          <div v-for="(article, index) in articles" :key="index" class="col-md-4">
            <nuxt-link :to="{ name: 'blog-slug', params:{slug: article.slug}}" class="d-block blog-card mb-3 mb-md-0">
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
    </section>
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
  async asyncData ({ $content, params }) {
    const articles = await $content('blog', params.slug).only(['title', 'desc', 'image', 'slug']).sortBy('createdAt', 'asc').fetch()
    return { articles }
  },
  data () {
    return {
      skills: [
        {
          title: 'HTML',
          image: require('@/assets/images/html.png'),
          desc: 'The HyperText Markup Language, or HTML is the standard markup language for documents designed to be displayed in a web browser. It can be assisted by technologies such as Cascading Style Sheets (CSS) and scripting languages such as JavaScript.'
        },
        {
          title: 'CSS',
          image: require('@/assets/images/css.png'),
          desc: 'Cascading Style Sheets (CSS) is a style sheet language used for describing the presentation of a document written in a markup language such as HTML. CSS is a cornerstone technology of the World Wide Web, alongside HTML and JavaScript.'
        },
        {
          title: 'JavaScript',
          image: require('@/assets/images/javascript.png'),
          desc: 'JavaScript often abbreviated as JS, is a programming language that conforms to the ECMAScript specification. JavaScript is high-level, often just-in-time compiled, and multi-paradigm. It has curly-bracket syntax, dynamic typing, prototype-based object-orientation, and first-class functions.'
        },
        {
          title: 'Vue.js',
          image: require('@/assets/images/vuejs.jpg'),
          desc: 'Vue.js (commonly referred to as Vue; pronounced /vjuː/, like "view") is an open-source model–view–viewmodel front end JavaScript framework for building user interfaces and single-page applications.'
        },
        {
          title: 'Bootstrap',
          image: require('@/assets/images/bootstrap.png'),
          desc: 'Bootstrap is a free and open-source CSS framework directed at responsive, mobile-first front-end web development. It contains CSS- and (optionally) JavaScript-based design templates for typography, forms, buttons, navigation, and other interface components.'
        },
        {
          title: 'Node.js',
          image: require('@/assets/images/nodejs-logo.png'),
          desc: 'Node.js is an open-source, cross-platform, back-end JavaScript runtime environment that runs on the V8 engine and executes JavaScript code outside a web browser. Node.js lets developers use JavaScript to write command line tools and for server-side scripting—running scripts server-side to produce dynamic web page content before the page is sent to the users web browser.'
        }
      ],
      works: [
        {
          id: 1,
          workTitle: 'Creative Agency',
          gitLink: 'https://github.com/ndanev/creative-agency',
          website: '',
          img: require('@/assets/images/creative-agency.jpg')
        },
        {
          id: 2,
          workTitle: 'Job Loop',
          gitLink: 'https://github.com/ndanev/JobLoop',
          website: '',
          img: require('@/assets/images/jobloop.jpg')
        },
        {
          id: 3,
          workTitle: 'Natural Tasty',
          gitLink: 'https://github.com/ndanev/Tastyland-Website',
          website: 'https://tastyland-website.netlify.app/',
          img: require('@/assets/images/tastyland.jpg')
        },
        {
          id: 4,
          workTitle: 'Project 4',
          gitLink: '',
          website: '',
          img: require('@/assets/images/work-4.png')
        },
        {
          id: 5,
          workTitle: 'Project 5',
          gitLink: '',
          website: '',
          img: require('@/assets/images/work-5.png')
        },
        {
          id: 6,
          workTitle: 'Project 6',
          gitLink: '',
          website: '',
          img: require('@/assets/images/work-6.png')
        },
        {
          id: 7,
          workTitle: 'Project 7',
          gitLink: '',
          website: '',
          img: require('@/assets/images/work-7.png')
        },
        {
          id: 8,
          workTitle: 'Project 8',
          gitLink: '',
          website: '',
          img: require('@/assets/images/work-8.png')
        }
      ],
      workProcess: [
        {
          id: 1,
          title: 'Planning',
          desc: 'A project plan is a series of formal documents that define the execution and control stages of a project. The plan includes considerations for risk management, resource management and communications, while also addressing scope, cost and schedule baselines.'
        },
        {
          id: 2,
          title: 'Designing',
          desc: 'Web design encompasses many different skills and disciplines in the production and maintenance of websites. The different areas of web design include web graphic design; user interface design (UI design); authoring, including standardised code and proprietary software; user experience design (UX design); and search engine optimization.'
        },
        {
          id: 3,
          title: 'Development',
          desc: 'Web development is the work involved in developing a website for the Internet (World Wide Web) or an intranet (a private network). Web development can range from developing a simple single static page of plain text to complex web applications, electronic businesses, and social network services.'
        },
        {
          id: 4,
          title: 'Testing',
          desc: 'Web testing is software testing that focuses on web applications. Complete testing of a web-based system before going live can help address issues before the system is revealed to the public. Issues may include the security of the web application, the basic functionality of the site, its accessibility to handicapped users and fully able users, its ability to adapt to the multitude of desktops, devices, and operating systems, as well as readiness for expected traffic and number of users and the ability to survive a massive spike in user traffic, both of which are related to load testing.'
        },
        {
          id: 5,
          title: 'Deployment',
          desc: 'Software deployment is all of the activities that make a software system available for use. The general deployment process consists of several interrelated activities with possible transitions between them. These activities can occur at the producer side or at the consumer side or both. Because every software system is unique, the precise processes or procedures within each activity can hardly be defined. Therefore, "deployment" should be interpreted as a general process that has to be customized according to specific requirements or characteristics.'
        },
        {
          id: 6,
          title: 'Maintenance',
          desc: 'Maintenance in software engineering is the modification of a software product after delivery to correct faults, to improve performance or other attributes. A common perception of maintenance is that it merely involves fixing defects. The key software maintenance issues are both managerial and technical. Key management issues are: alignment with customer priorities, staffing, which organization does maintenance, estimating costs. Key technical issues are: limited understanding, impact analysis, testing, maintainability measurement.'
        }
      ]
    }
  },
  methods: {
    sendMessage () {
      alert('Coming Soon...')
    }
  }
}
</script>

<style>
.hero-home {
  background-image: url("@/assets/images/hero-home.jpg");
  background-repeat: no-repeat;
  background-size: cover;
  height: calc(100vh - 30px - 85px);
  width: 100%;
}

.hero-home-title {
  color: #ffffff;
  font-size: 4rem;
  font-weight: bold;
  text-transform: uppercase;
}

.hero-home-title span {
  color: #f33c7a;
}

.hero-lead {
  color: #ffffff;
  font-size: 1.6rem;
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

.blog-card {
  position: relative;
}

.blog-card .details {
  background: rgba(45, 25, 72, .6);
  color: #fff;
  padding: 1rem;
  position: absolute;
  top: 0;
  left: 0;
  bottom: 0;
  right: 0;
  border-radius: 10px;
  display: flex;
  flex-direction: column;
  justify-content: flex-end;
}

.blog-card .details:hover {
  background: rgba(45, 25, 72, .8);
  text-decoration: underline;
}

.blog-card .details h3 {
  font-weight: bold;
  font-size: 1.2rem;
  text-transform: uppercase;
}

.blog-card img {
  height: 250px;
  width: 100%;
  object-fit: cover;
  border-radius: 10px;
}

.section-contact {
  background-image: url("@/assets/images/home-contact-bg.png");
  background-color: rgba(27, 12, 48, .8);
  background-repeat: no-repeat;
  background-position: center;
  background-size: cover;
}

.section-contact .section-title {
  margin-bottom: 2rem;
}

.home-form label {
  color: #fff;
  font-weight: bold;
}

.home-form .form-control {
  background-color: #2d1948;
  color: #fff;
  border-radius: 0;
  border: 0;
  height: 45px;
}

.home-form .form-control::placeholder {
  color: #fff;
}

.home-form textarea {
  background-color: #2d1948;
  color: #fff;
  border-radius: 0;
  border: 0;
  padding: 1rem;
}

@media (max-width: 991px) {
  .hero-home {
    background-position: 75%;
  }
}

@media (max-width: 767px) {
  .hero-lead {
    font-size: 1.2rem;
  }

  .hero-home-title {
    font-size: 2.6rem;
  }

  .column {
    padding: 5px 10px;
  }
}
</style>
