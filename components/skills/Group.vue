<template>
  <div>
    <section class="group-title">
      <h3 class="group-title-item">{{ title }}</h3>
      <v-spacer></v-spacer>
      <a v-scroll-to="{ el: '#top' }" href="#" class="group-title-item">Back to Top</a>
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
  @apply self-center;
  @apply flex;
  @apply flex-col;
  @apply flex-nowrap;
  @apply justify-center;
  @apply m-6;
  @apply p-2;
  @apply w-11/12;
}
.group-title {
  @apply self-center;
  @apply flex;
  @apply flex-row;
  @apply flex-nowrap;
  @apply justify-around;
  @apply w-full;
}
.group-title-item {
  @apply w-60;
  @apply text-center;
}
h3 {
  @apply font-medium;
}
a {
  @apply text-black;
  @apply underline;
}
.skill-container {
  @apply flex;
  @apply flex-row;
  @apply flex-wrap;
  @apply w-full;
}
</style>
