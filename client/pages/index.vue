<template>
  <div class="home">
    <div class="hero-home">
      <div class="container h-100">
        <div class="row h-100">
          <div class="col-md-7 offset d-flex justify-content-center flex-column">
            <h2 class="hero-home-title animate-4">
              Online <br> Creative
              <span>Agency</span>
            </h2>
            <p class="hero-lead mb-5 animate-6">
              {{ homeContent.heroSubtitle }}
            </p>
            <div class="hero-button-wrapper animate-8">
              <a class="button button-primary" href="mailto:nemanja.danev.93@gmail.com">
                {{ homeContent.heroButton }}
              </a>
            </div>
          </div>
        </div>
      </div>
    </div>
    <section class="section section-about">
      <div class="container">
        <div class="row">
          <div class="col-md-12 text-left text-md-center">
            <h2 class="section-title">
              <span>
                {{ homeContent.aboutTitle }}
              </span>
            </h2>
          </div>
        </div>
        <div class="row">
          <div class="col-md-6 d-flex flex-column justify-content-center">
            <h2 class="section-subtitle">
              We are a
              <br>
              <span>Creative Agency</span>
            </h2>
            <p class="section-lead">
              {{ homeContent.aboutContent }}
            </p>
          </div>
          <div class="col-md-6 text-center">
            <img src="@/assets/images/home-about.webp" class="img-fluid" alt="Creative Agency" title="Creative Agency">
          </div>
        </div>
      </div>
    </section>
    <section class="section section-skills">
      <div class="container">
        <div class="row justify-content-center mb-5">
          <div class="col-md-6 text-center">
            <h2 class="section-title">
              <span>
                {{ homeContent.skillsTitle }}
              </span>
            </h2>
            <p class="section-lead">
              {{ homeContent.skillsSubtitle }}
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
            <h2 class="section-title">
              <span>
                {{ homeContent.worksTitle }}
              </span>
            </h2>
            <p class="section-lead">
              {{ homeContent.worksSubtitle }}
            </p>
          </div>
        </div>
        <div class="row justify-content-center">
          <div v-for="work in works" :key="work.id" class="col-12 col-sm-6 col-md-3">
            <nuxt-link to="/works">
              <WorkCard :title="work.workTitle" :image="work.img" />
            </nuxt-link>
          </div>
        </div>
      </div>
    </section>
    <section class="section section-process">
      <div class="container">
        <div class="row justify-content-center mb-5">
          <div class="col-md-6 text-center">
            <h2 class="section-title">
              <span>
                {{ homeContent.processTitle }}
              </span>
            </h2>
            <p class="section-lead">
              {{ homeContent.processSubtitle }}
            </p>
          </div>
        </div>
        <div class="row">
          <div v-for="(process, index) in workProcess" :key="index" class="col-12 col-sm-6 col-md-4">
            <ProcessCard :title="process.title" :desc="process.desc" />
          </div>
        </div>
      </div>
    </section>
    <section class="section section-blog">
      <div class="container-fluid">
        <div class="row justify-content-center">
          <div class="col-md-6 text-center">
            <h2 class="section-title">
              <span>
                {{ homeContent.blogsTitle }}
              </span>
            </h2>
          </div>
        </div>
        <div class="row">
          <div v-for="(article, index) in articles" :key="index" class="col-md-4">
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
    <section class="section section-contact">
      <div class="container">
        <div class="row justify-content-center mb-5">
          <div class="col-md-6 text-center">
            <h2 class="section-title">
              <span>
                {{ homeContent.contactTitle }}
              </span>
            </h2>
            <p class="section-lead">
              {{ homeContent.contactSubtitle }}
            </p>
          </div>
        </div>
        <div class="row">
          <div class="col-md-12">
            <form class="home-form" @submit.prevent="sendMessage">
              <div class="row">
                <div class="col-md-4">
                  <div class="form-group">
                    <label>{{ homeContent.contactLabelTitle }}</label>
                    <input type="text" class="form-control" :placeholder="homeContent.contactPlaceholderTitle">
                  </div>
                </div>
                <div class="col-md-4">
                  <div class="form-group">
                    <label>{{ homeContent.contactLabelName }}</label>
                    <input type="text" class="form-control" :placeholder="homeContent.contactPlaceholderName">
                  </div>
                </div>
                <div class="col-md-4">
                  <div class="form-group">
                    <label>{{ homeContent.contactLabelEmail }}</label>
                    <input type="text" class="form-control" :placeholder="homeContent.contactPlaceholderEmail">
                  </div>
                </div>
              </div>
              <div class="row">
                <div class="col-md-12">
                  <div class="form-colntrol">
                    <label>{{ homeContent.contactLabelMessage }}</label>
                    <textarea class="form-group w-100" rows="10" />
                  </div>
                </div>
              </div>
              <div class="row">
                <div class="col-md-12">
                  <button type="submit" class="button button-primary">
                    {{ homeContent.contactButton }}
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
      homeContent:
        {
          heroSubtitle: 'Looking for someone to realize your digital dreams? You’ve come to the right place!',
          heroButton: 'Contact Us',
          aboutTitle: 'About Us',
          aboutContent: 'With a strong sense of aesthetic and an eye for pixel perfection, we pair with our clients to create the best versions of their design ideas. We offer elegant solutions and user experiences which enhance the online presence of a wide variety of businesses. Our team is ready for whatever it is your heart desires, willing to go the extra mile to create your perfect project.',
          skillsTitle: 'Our Skills',
          skillsSubtitle: 'With professionals in all areas of web development, rest assured that your projects will be completed and presented online with pixel-precision.',
          worksTitle: 'Our Works',
          worksSubtitle: 'Browse through our completed projects to get an idea of what we can do for you.',
          processTitle: 'Work Process',
          processSubtitle: 'Our clients peace of mind is our number one priority. We are a team and we will work together with you on every step of the way to bring your ideas to life.',
          blogsTitle: 'Latest Blogs',
          contactTitle: 'Contact',
          contactSubtitle: 'If you have any question or you want to contact us, feel free to send us an email. We’re here to help you!',
          contactLabelTitle: 'Your Title',
          contactPlaceholderTitle: 'Enter Your Title',
          contactLabelName: 'Your Name',
          contactPlaceholderName: 'Enter Your Name',
          contactLabelEmail: 'Your Email',
          contactPlaceholderEmail: 'Enter Your Email',
          contactLabelMessage: 'Your Message',
          contactButton: 'Send'
        },
      skills: [
        {
          title: 'HTML',
          image: require('@/assets/images/html.jpg'),
          desc: 'The HyperText Markup Language, or HTML is the standard markup language for documents designed to be displayed in a web browser. It can be assisted by technologies such as Cascading Style Sheets (CSS) and scripting languages such as JavaScript.'
        },
        {
          title: 'CSS',
          image: require('@/assets/images/css.jpg'),
          desc: 'Cascading Style Sheets (CSS) is a style sheet language used for describing the presentation of a document written in a markup language such as HTML. CSS is a cornerstone technology of the World Wide Web, alongside HTML and JavaScript.'
        },
        {
          title: 'JavaScript',
          image: require('@/assets/images/javascript.jpg'),
          desc: 'JavaScript often abbreviated as JS, is a programming language that conforms to the ECMAScript specification. JavaScript is high-level, often just-in-time compiled, and multi-paradigm. It has curly-bracket syntax, dynamic typing, prototype-based object-orientation, and first-class functions.'
        },
        {
          title: 'Vue.js',
          image: require('@/assets/images/vuejs.jpg'),
          desc: 'Vue.js (commonly referred to as Vue; pronounced /vjuː/, like "view") is an open-source model–view–viewmodel front end JavaScript framework for building user interfaces and single-page applications.'
        },
        {
          title: 'Bootstrap',
          image: require('@/assets/images/bootstrap.jpg'),
          desc: 'Bootstrap is a free and open-source CSS framework directed at responsive, mobile-first front-end web development. It contains CSS- and (optionally) JavaScript-based design templates for typography, forms, buttons, navigation, and other interface components.'
        },
        {
          title: 'Node.js',
          image: require('@/assets/images/nodejs-logo.webp'),
          desc: 'Node.js is an open-source, cross-platform, back-end JavaScript runtime environment that runs on the V8 engine and executes JavaScript code outside a web browser. Node.js lets developers use JavaScript to write command line tools and for server-side scripting—running scripts server-side to produce dynamic web page content before the page is sent to the users web browser.'
        }
      ],
      works: [
        {
          id: 1,
          workTitle: 'Job Loop',
          img: require('@/assets/images/jobloop.webp')
        },
        {
          id: 2,
          workTitle: 'Github User Finder',
          img: require('@/assets/images/user-finder.webp')
        },
        {
          id: 3,
          workTitle: 'Natural Tasty',
          img: require('@/assets/images/tastyland.webp')
        },
        {
          id: 4,
          workTitle: 'Creative Agency',
          img: require('@/assets/images/creative-agency.webp')
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
  head () {
    return {
      title: 'Online Creative Agency',
      meta: [
        {
          hid: 'description',
          name: 'description',
          content: 'Looking for someone to realize your digital dreams? You’ve come to the right place!'
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

<style>
.hero-home {
  background-image: url("@/assets/images/hero-home.webp");
  background-color: rgba(45, 25, 72, 1);
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
  -webkit-animation: .4s ease-out 0s 1 slideInFromLeft;
          animation: .4s ease-out 0s 1 slideInFromLeft;
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

.section-process {
  background-image: url("@/assets/images/work-process-bg.webp");
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
  display: -webkit-box;
  display: -ms-flexbox;
  display: flex;
  -webkit-box-orient: vertical;
  -webkit-box-direction: normal;
      -ms-flex-direction: column;
          flex-direction: column;
  -webkit-box-pack: end;
      -ms-flex-pack: end;
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
  height: 350px;
  width: 100%;
  -o-object-fit: cover;
     object-fit: cover;
  border-radius: 10px;
}

.section-contact {
  background-image: url("@/assets/images/contact-bg.webp");
  background-repeat: no-repeat;
  background-position: center;
  background-size: cover;
  position: relative;
  z-index: 1;
}

.section-contact::after {
  content: '';
  position: absolute;
  top: 0;
  left: 0;
  bottom: 0;
  right: 0;
  width: 100%;
  height: 100%;
  background-color: rgba(27, 12, 48, .35);
  z-index: -1;
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

.home-form .form-control::-webkit-input-placeholder {
  color: #fff;
}

.home-form .form-control::-moz-placeholder {
  color: #fff;
}

.home-form .form-control:-ms-input-placeholder {
  color: #fff;
}

.home-form .form-control::-ms-input-placeholder {
  color: #fff;
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

@-webkit-keyframes slideInFromLeft {
  0% {
    -webkit-transform: translateX(-100%);
            transform: translateX(-100%);
  }
  100% {
    -webkit-transform: translateX(0);
            transform: translateX(0);
  }
}

@keyframes slideInFromLeft {
  0% {
    -webkit-transform: translateX(-100%);
            transform: translateX(-100%);
  }
  100% {
    -webkit-transform: translateX(0);
            transform: translateX(0);
  }
}

.animate-8 {
  -webkit-animation: .8s ease-out 0s 1 slideInFromLeft;
          animation: .8s ease-out 0s 1 slideInFromLeft;
}

.animate-6 {
  -webkit-animation: .6s ease-out 0s 1 slideInFromLeft;
          animation: .6s ease-out 0s 1 slideInFromLeft;
}

.animate-4 {
  -webkit-animation: .4s ease-out 0s 1 slideInFromLeft;
          animation: .4s ease-out 0s 1 slideInFromLeft;
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
}
</style>
