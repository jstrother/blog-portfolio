<template>
  <div class="card">
    <h3>{{ name }}</h3>
    <img :src="image" :alt="`${name} Logo`" :title="name" />
    <div class="skill-bar">
      <div class="skill-container">
        <div class="skills" :style="skillBar">{{ level }}%</div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    name: {
      type: String,
      required: true,
    },
    level: {
      type: Number,
      required: true,
    },
    bgColor: {
      type: String,
      required: true,
    },
    image: {
      type: String,
      required: true,
    },
  },
  computed: {
    skillBar() {
      return {
        '--bg-color': this.bgColor,
        '--skill-width': `${this.level}%`,
      };
    },
  },
};
</script>

<style scoped>
.card {
  @apply flex flex-col flex-nowrap w-96 md:w-80 m-2 p-2 border-2 border-gray-300 rounded-lg shadow-lg bg-gray-50 animate-fadeIn3s;
}
h3 {
  @apply font-medium;
}
img {
  @apply m-2 w-12 md:w-28 h-12 md:h-28 rounded-md;
}

.skill-bar {
  @apply box-border;
}
.skill-container {
  @apply w-full bg-gray-300 rounded-md;
}
.skills {
  background-color: var(--bg-color);
  width: var(--skill-width);
  @apply text-sm md:text-base lg:text-xl text-right text-white p-4 rounded-l-md;
}
</style>
