<template>
  <div class="work">
    <div class="hero">
      <div class="container">
        <div class="row">
          <div class="col-md-12">
            <h1 class="hero-title">
              Portfolio
            </h1>
            <p class="hero-lead">
              Personal <span>Projects</span>
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
                <img :src="project.image" class="img-fluid" alt>
              </div>
              <div class="col-md-6 d-flex flex-column justify-content-center">
                <h3 class="project-title">
                  {{ project.title }}
                </h3>
                <p class="project-desc">
                  {{ project.desc }}
                </p>
                <div class="mb-1">
                  - <a :href="project.githubLink" class="project-link" target="_blank">Github Link <i class="fas fa-external-link-alt" /></a>
                </div>
                <div>
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
      projects: [
        {
          id: 1,
          title: 'Job Loop',
          image: require('@/assets/images/jobloop.jpg'),
          desc: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.',
          githubLink: 'https://github.com/ndanev/JobLoop/',
          website: ''
        },
        {
          id: 2,
          title: 'Github User Finder',
          image: require('@/assets/images/user-finder.jpg'),
          desc: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.',
          githubLink: 'https://github.com/ndanev/user-finder',
          website: 'https://online-user-finder.netlify.app/'
        },
        {
          id: 3,
          title: 'Tastyland',
          image: require('@/assets/images/tastyland.jpg'),
          desc: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.',
          githubLink: 'https://github.com/ndanev/Tastyland-Website',
          website: 'https://tastyland-website.netlify.app/'
        },
        {
          id: 4,
          title: 'Online Creative Agency',
          image: require('@/assets/images/creative-agency.jpg'),
          desc: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.',
          githubLink: 'https://github.com/ndanev/creative-agency',
          website: 'https://online-agency.herokuapp.com/'
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

.project-link {
  color: #2d1948;
  font-weight: bold;
  transition: all .25s;
}

.project-link i {
  color: #f33c7a;
}

.project-link:hover {
  color: #f33c7a;
}
</style>
