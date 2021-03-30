<template>
  <main id="top" class="skills">
    <section class="title-bar">
      <h1>Skills</h1>
      <br />
      <nav>
        <a
          v-for="(group, index) in groupings"
          :key="index"
          v-scroll-to="{ el: `#${group.title.toLowerCase()}` }"
          href="#"
        >
          {{ group.title }}
        </a>
      </nav>
    </section>
    <section
      v-for="(group, index) in groupings"
      :id="group.title.toLowerCase()"
      :key="index"
      class="skill-section"
    >
      <br />
      <br />
      <Group class="skill-group" :title="group.title" :skills="group.skills" />
    </section>
  </main>
</template>

<script>
import Group from '~/components/skills/Group';

export default {
  components: {
    Group,
  },
  async asyncData({ $content }) {
    const skillsList = await $content('skills').fetch();
    // remember, fetch() returns an array!
    const skills = skillsList[0].skills;

    const groupings = [
      {
        title: 'Front-End',
        skills: skills.front,
      },
      {
        title: 'Back-End',
        skills: skills.back,
      },
      {
        title: 'Testing',
        skills: skills.testing,
      },
      {
        title: 'General',
        skills: skills.general,
      },
      {
        title: 'Other',
        skills: skills.other,
      },
    ];

    return { groupings };
  },
};
</script>

<style scoped>
main {
  @apply flex flex-col flex-nowrap justify-around bg-gray-200 p-14 mb-auto;
}
.title-bar {
  @apply flex flex-col flex-nowrap justify-center items-center;
}
h1 {
  @apply text-2xl font-bold p-2.5;
}
nav {
  @apply flex flex-row flex-nowrap;
}
a {
  @apply text-black underline m-2;
}
.skill-section {
  @apply flex flex-col flex-nowrap justify-around;
}
</style>
