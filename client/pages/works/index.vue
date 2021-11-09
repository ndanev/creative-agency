<template>
  <div class="work">
    <div class="hero">
      <div class="container">
        <div class="row">
          <div class="col-md-12">
            <h1 class="hero-title">
              {{ worksContent.heroTitle }}
            </h1>
            <p class="hero-lead">
              {{ worksContent.heroSubtitle }} <span>{{ worksContent.heroSubtitleAddition }}</span>
            </p>
          </div>
        </div>
      </div>
    </div>
    <div class="section">
      <div class="container">
        <div class="row">
          <div v-for="project in projects" :key="project.id" class="col-md-12 mb-5 project">
            <div class="row">
              <div class="col-md-6 mb-3 mb-md-0">
                <img
                  :src="project.image"
                  class="img-fluid"
                  width="402"
                  height="313"
                  :alt="project.title"
                  :title="project.title"
                >
              </div>
              <div class="col-md-6 d-flex flex-column justify-content-center">
                <h3 class="project-title">
                  {{ project.title }}
                </h3>
                <div class="project-subtitle">
                  {{ project.subtitle }}
                </div>
                <p class="project-desc">
                  {{ project.desc }} <br>
                  {{ project.technologies }} <br>
                  <em>{{ project.responsive }}</em>
                </p>
                <div v-if="project.githubLink" class="mb-1">
                  - <a :href="project.githubLink" class="project-link" target="_blank">Github Link <i class="fas fa-external-link-alt" /></a>
                </div>
                <div v-if="project.website">
                  - <a :href="project.website" class="project-link" target="_blank">Website <i class="fas fa-external-link-alt" /></a>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data () {
    return {
      worksContent: {
        heroTitle: 'Portfolio',
        heroSubtitle: 'Personal',
        heroSubtitleAddition: 'Projects'
      },
      projects: [
        {
          id: 1,
          title: 'Job Loop',
          subtitle: '(Online Job Search Application)',
          image: require('@/assets/images/jobloop.webp'),
          desc: '- Browsing for job opportunities can be done as a guest, with the ability to register if they wish to apply or to post their own job.',
          technologies: '- The technologies used include HTML, CSS, Javascript, VueJS, NodeJS and MongoDB.',
          responsive: '- Full Responsive',
          githubLink: 'https://github.com/ndanev/JobLoop/',
          website: ''
        },
        {
          id: 2,
          title: 'Github User Finder',
          subtitle: '(Online GitHub User Finder Application)',
          image: require('@/assets/images/user-finder.webp'),
          desc: '- Created an application that allows users to search for GitHub profiles, and allows them to view the profiles and repositories. Created by fetching the GitHub API.',
          technologies: '- Technology used: HTML, CSS(SCSS), Javascript, Vue.js, Bootstrap, Axios',
          responsive: '- Full Responsive',
          githubLink: 'https://github.com/ndanev/user-finder',
          website: 'https://online-user-finder.netlify.app/'
        },
        {
          id: 3,
          title: 'Tastyland',
          subtitle: '(Online Tastyland Website)',
          image: require('@/assets/images/tastyland.webp'),
          desc: '- Convert PSD file (Photoshop) to HTML, CSS and Javascript',
          technologies: '- Technology used: HTML, CSS, Javascript, Bootstrap',
          responsive: '- Full Responsive',
          githubLink: 'https://github.com/ndanev/Tastyland-Website',
          website: 'https://tastyland-website.netlify.app/'
        },
        {
          id: 4,
          title: 'Online Creative Agency',
          subtitle: '(Creative Agency Website – Personal Portfolio)',
          image: require('@/assets/images/creative-agency.webp'),
          desc: '- Created a website for a creative agency which serves as a presentation of my personal portfolio. Design template taken from a free PSD website.',
          technologies: '- Technology used: HTML, CSS, Bootstrap, Javascript, Nuxt.js (Vue.js), Axios',
          responsive: '- Full Responsive',
          githubLink: 'https://github.com/ndanev/creative-agency',
          website: 'https://online-agency.herokuapp.com/'
        }
      ]
    }
  },
  head () {
    return {
      title: 'Our Works | Online Creative Agency',
      meta: [
        {
          hid: 'description',
          name: 'description',
          content: 'Browse through our completed projects to get an idea of what we can do for you.'
        }
      ]
    }
  }
}
</script>

<style>
.work .hero-title {
  padding-bottom: 0;
  margin-bottom: 1rem;
}

.work .hero-lead {
  margin-bottom: 40px;
}

.work .hero-lead span {
  color: #f33c7a;
}

.project img {
  border: 1px solid #d9d9d9;
}

.project-link {
  color: #2d1948;
  font-weight: bold;
  -webkit-transition: all .25s;
  -o-transition: all .25s;
  transition: all .25s;
}

.project-link i {
  color: #f33c7a;
}

.project-link:hover {
  color: #f33c7a;
}

.project-subtitle {
  font-size: 1rem;
  margin-bottom: .8rem;
  font-weight: 500;
}
</style>
