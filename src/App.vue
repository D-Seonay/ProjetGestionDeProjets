<template>
  <div id="app" class="app">
    <HeaderComponent />
    <AddProjectForm @submit-project="addProject" />
    <ProjectList v-if="projects.length > 0" :projects="projects" @select-project="selectProject" />
    <p v-else>Aucun projet pour le moment.</p>
    <ProjectItem v-if="selectedProject" :project="selectedProject" />
    <FooterComponent />

  </div>
</template>

<script>
import HeaderComponent from './components/HeaderComponent.vue';
import ProjectList from './components/ProjectList.vue';
import ProjectItem from './components/ProjectItem.vue';
import AddProjectForm from './components/AddProjectForm.vue';
import FooterComponent from './components/FooterComponent.vue';

export default {
  data() {
    return {
      projects: [],
      selectedProject: null
    };
  },
  methods: {
    addProject(project) {
      this.projects.push(project);
    },
    selectProject(project) {
      this.selectedProject = project;
    }
  },
  components: {
    HeaderComponent,
    ProjectList,
    ProjectItem,
    AddProjectForm,
    FooterComponent
  }
};
</script>

<style>

@import url('https://fonts.googleapis.com/css?family=Poppins:100,100italic,200,200italic,300,300italic,regular,italic,500,500italic,600,600italic,700,700italic,800,800italic,900,900italic');

#app {
  font-family: 'Poppins', sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #191919;
}

* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}

h1 {
  color: #191919;
}

.app {
  display: flex;
  flex-direction: column;
  justify-content: center;
}


</style>