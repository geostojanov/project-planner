<template>
  <div class="home">
    <div v-if="projects.length">
      <div :key="project.id" v-for="project in projects">
        <p>{{ project.title }}</p>
      </div>
    </div>
  </div>
</template>

<script>
// @ is an alias to /src

export default {
  name: 'HomeView',
  components: {},
  data() {
    return {
      projects: []
    }
  },
  mounted() {
    fetch('http://localhost:3000/projects')
      .then(res => res.json())
      .then(data => this.projects = data)
      .catch(err => console.log(err.message))
  }
}
</script>
