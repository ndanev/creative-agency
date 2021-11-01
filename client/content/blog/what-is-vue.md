---
title: What is Vue?
desc: Vue.js is an open-source model–view–viewmodel front end JavaScript framework for building user interfaces and single-page applications. It was created by Evan You, and is maintained by him and the rest of the active core team members.
slug: what-is-vue
image: vue.jpg
---

![Vue](../../_nuxt/assets/images/vue.jpg)

Vue.js is an open-source model–view–viewmodel front end JavaScript framework for building user interfaces and single-page applications. It was created by Evan You, and is maintained by him and the rest of the active core team members.

### Overview

Vue.js features an incrementally adaptable architecture that focuses on declarative rendering and component composition. The core library is focused on the view layer only. Advanced features required for complex applications such as routing, state management and build tooling are offered via officially maintained supporting libraries and packages.

Vue.js allows for extending HTML with HTML attributes called directives. The directives offer functionality to HTML applications, and come as either built-in or user defined directives.

### History

Vue was created by Evan You after working for Google using AngularJS in a number of projects. He later summed up his thought process: "I figured, what if I could just extract the part that I really liked about Angular and build something really lightweight." The first source code commit to the project was dated July 2013, and Vue was first released the following February, in 2014.

Version names are often derived from manga and anime, most of which are within the science fiction genre.

### Components

Vue components extend basic HTML elements to encapsulate reusable code. At a high level, components are custom elements to which the Vue's compiler attaches behavior. In Vue, a component is essentially a Vue instance with pre-defined options. The code snippet below contains an example of a Vue component. The component presents a button and prints the number of times the button is clicked:

```
<template>
  <div id="tuto">
    <button-clicked v-bind:initial-count="0"></button-clicked>
  </div>
</template>

<script>
Vue.component('button-clicked', {
  props: ['initialCount'],
  data: () => ({
    count: 0,
  }),
  template: '<button v-on:click="onClick">Clicked {{ count }} times</button>',
  computed: {
    countTimesTwo() {
      return this.count * 2;
    }
  },
  watch: {
    count(newValue, oldValue) {
      console.log(`The value of count is changed from ${oldValue} to ${newValue}.`);
    }
  },
  methods: {
    onClick() {
      this.count += 1;
    }
  },
  mounted() {
    this.count = this.initialCount;
  }
});

new Vue({
  el: '#tuto',
});
</script>

```

### Templates

Vue uses an HTML-based template syntax that allows binding the rendered DOM to the underlying Vue instance's data. All Vue templates are valid HTML that can be parsed by specification-compliant browsers and HTML parsers. Vue compiles the templates into virtual DOM render functions. A virtual Document Object Model (or “DOM”) allows Vue to render components in its memory before updating the browser. Combined with the reactivity system, Vue is able to calculate the minimal number of components to re-render and apply the minimal amount of DOM manipulations when the app state changes.

Vue users can use template syntax or choose to directly write render functions using hyperscript either through function calls or JSX. Render functions allow application to be built from software components.

### Reactivity

Vue features a reactivity system that uses plain JavaScript objects and optimized re-rendering. Each component keeps track of its reactive dependencies during its render, so the system knows precisely when to re-render, and which components to re-render.

### Routing

A traditional disadvantage of single-page applications (SPAs) is the inability to share links to the exact "sub" page within a specific web page. Because SPAs serve their users only one URL-based response from the server (it typically serves index.html or index.vue), bookmarking certain screens or sharing links to specific sections is normally difficult if not impossible. To solve this problem, many client-side routers delimit their dynamic URLs with a "hashbang" (#!), e.g. page.com/#!/. However, with HTML5 most modern browsers support routing without hashbangs.

Vue provides an interface to change what is displayed on the page based on the current URL path – regardless of how it was changed (whether by emailed link, refresh, or in-page links). Additionally, using a front-end router allows for the intentional transition of the browser path when certain browser events (i.e. clicks) occur on buttons or links. Vue itself doesn’t come with front-end hashed routing. But the open source "vue-router" package provides an API to update the application's URL, supports the back button (navigating history), and email password resets or email verification links with authentication URL parameters. It supports mapping nested routes to nested components and offers fine-grained transition control. With Vue, developers are already composing applications with small building blocks building larger components. With vue-router added to the mix, components must merely be mapped to the routes they belong to, and parent/root routes must indicate where children should render.

```
<div id="app">
  <router-view></router-view>
</div>
...

<script>
...
const User = {
  template: '<div>User {{ $route.params.id }}</div>'
};

const router = new VueRouter({
  routes: [
    { path: '/user/:id', component: User }
  ]
});
...
</script>

```

1. Sets a front-end route at **websitename.com/user/id**
2. Which will render in the User component defined in (const User...)
3. Allows the User component to pass in the particular id of the user which was typed into the URL using the $route object's params key: **$route.params.id**
4. This template (varying by the params passed into the router) will be rendered into ``` <router-view></router-view> ``` inside the DOM's div#app.
5. The finally generated HTML for someone typing in: **websitename.com/user/1** will be:

```
<div id="app">
  <div>
    <div>User 1</div>
  </div>
</div>

```