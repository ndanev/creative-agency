<template>
  <div>
    <div class="hero">
      <div class="container">
        <div class="row">
          <div class="col-md-12 text-center">
            <h1 class="hero-title">
              Process
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
        <div class="row">
          <div v-for="(skill, index) in skills" :key="index" class="col-6 col-md-4">
            <SkillCard :title="skill.title" :image="skill.image" />
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
          image: require('@/assets/images/html.png'),
          num: '7'
        },
        {
          title: 'CSS',
          image: require('@/assets/images/css.png'),
          num: '10'
        },
        {
          title: 'JavaScript',
          image: require('@/assets/images/javascript.png'),
          num: '250'
        },
        {
          title: 'Vue.js',
          image: require('@/assets/images/vuejs.jpg'),
          num: '98%'
        },
        {
          title: 'Bootstrap',
          image: require('@/assets/images/bootstrap.png'),
          num: '98%'
        },
        {
          title: 'Node.js',
          image: require('@/assets/images/nodejs-logo.png'),
          num: '98%'
        }
      ]
    }
  }
}
</script>
