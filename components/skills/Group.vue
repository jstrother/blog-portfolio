<template>
  <div>
    <section class="group-title">
      <h3 class="group-title-item">{{ title }}</h3>
      <a v-if="title !== 'Front-End'" v-scroll-to="{ el: '#top' }" href="#" class="group-title-item"
        >Back to Top</a
      >
    </section>
    <div class="skill-container">
      <Display
        v-for="(skill, index) of skills"
        :key="index"
        class="skill-display"
        :name="skill.name"
        :level="skill.level"
        :bg-color="skill.bgColor"
        :image="skill.image"
      />
    </div>
  </div>
</template>

<script>
import Display from '~/components/skills/Display';

export default {
  components: {
    Display,
  },
  props: {
    title: {
      type: String,
      required: true,
    },
    skills: {
      type: Array,
      required: true,
    },
  },
};
</script>

<style scoped>
div {
  @apply self-center flex flex-col flex-nowrap justify-center m-6 w-11/12;
}
.group-title {
  @apply self-center flex flex-row flex-nowrap justify-around w-full;
}
.group-title-item {
  @apply w-60 text-center;
}
h3 {
  @apply font-medium;
}
a {
  @apply text-black underline;
}
.skill-container {
  @apply flex flex-row flex-wrap w-full;
}
</style>
