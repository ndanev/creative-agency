<template>
  <div class="process">
    <div class="hero">
      <div class="container">
        <div class="row">
          <div class="col-md-12">
            <h1 class="hero-title">
              {{ processContent.heroTitle }}
            </h1>
          </div>
        </div>
      </div>
    </div>
    <section class="section section-process">
      <div class="container">
        <div class="row">
          <div v-for="(process, index) in workProcess" :key="index" class="col-12 col-sm-6 col-md-4">
            <ProcessCard :id="process.id" :title="process.title" :desc="process.desc" />
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
                {{ processContent.skillsTitle }}
              </span>
            </h2>
            <p class="section-lead">
              {{ processContent.skillsSubtitle }}
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
  </div>
</template>

<script>
export default {
  data () {
    return {
      processContent: {
        heroTitle: 'Process',
        skillsTitle: 'Our Skills',
        skillsSubtitle: 'With professionals in all areas of web development, rest assured that your projects will be completed and presented online with pixel-precision.'
      },
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
      ],
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
          image: require('@/assets/images/nodejs-logo.png'),
          desc: 'Node.js is an open-source, cross-platform, back-end JavaScript runtime environment that runs on the V8 engine and executes JavaScript code outside a web browser. Node.js lets developers use JavaScript to write command line tools and for server-side scripting—running scripts server-side to produce dynamic web page content before the page is sent to the users web browser.'
        }
      ]
    }
  },
  head () {
    return {
      title: 'Work process | Online Creative Agency',
      meta: [
        {
          hid: 'description',
          name: 'description',
          content: 'With professionals in all areas of web development, rest assured that your projects will be completed and presented online with pixel-precision.'
        }
      ]
    }
  }
}
</script>
