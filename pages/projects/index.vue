<template>
  <main>
    <section class="title-bar">
      <h1>Projects</h1>
    </section>
    <hr />
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
  @apply flex;
  @apply flex-col;
  @apply flex-nowrap;
  @apply justify-around;
  @apply mb-auto;
}
.title-bar {
  @apply flex;
  @apply flex-col;
  @apply items-center;
}
h1 {
  @apply text-2xl;
  @apply font-bold;
  @apply p-2.5;
}
.projects-group {
  @apply flex;
  @apply flex-row;
  @apply flex-wrap;
  @apply justify-around;
  @apply mt-2;
}
</style>
