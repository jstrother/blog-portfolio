<template>
  <main>
    <section class="title-bar">
      <h1>Projects</h1>
    </section>
    <section class="projects-group">
      <ProjectCard
        v-for="(project, index) in projects"
        :key="index"
        :name="project.name"
        :image="project.image"
        :description="project.description"
        :git-hub="project.gitHub"
        :live-example="project.liveExample"
      />
    </section>
  </main>
</template>

<script>
import ProjectCard from '~/components/projects/ProjectCard';

export default {
  components: {
    ProjectCard,
  },
  async asyncData({ $content }) {
    const projectsList = await $content('projects').fetch();
    // remember that fetch() returns an array!
    const projects = projectsList[0].projects;

    return { projects };
  },
};
</script>

<style scoped>
main {
  @apply flex flex-col flex-nowrap justify-around mb-auto p-14 bg-gray-200;
}
.title-bar {
  @apply flex flex-col items-center;
}
h1 {
  @apply text-2xl font-bold p-2.5;
}
.projects-group {
  @apply flex flex-row flex-wrap justify-around mt-2;
}
</style>
