<template>
  <main id="top" class="skills">
    <section class="title-bar">
      <nav>
        <a
          v-for="(group, index) in groupings"
          :key="index"
          v-scroll-to="{ el: `#${group.title.toLowerCase()}` }"
          href="#"
        >
          <span v-if="group.title !== 'Front-End'">{{ group.title }}</span>
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
  @apply flex flex-col flex-nowrap justify-around bg-gray-200 px-4 pt-14 mb-auto;
}
.title-bar {
  @apply flex flex-col flex-nowrap justify-center items-center;
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
