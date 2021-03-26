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
  @apply flex;
  @apply flex-col;
  @apply flex-nowrap;
  @apply w-40;
  @apply md:w-80;
  @apply m-2;
  @apply p-2;
  @apply border-2;
  @apply border-gray-300;
  @apply rounded-lg;
  @apply shadow-lg;
  @apply bg-gray-50;
}
h3 {
  @apply font-medium;
}
img {
  @apply m-2;
  @apply w-12;
  @apply md:w-28;
  @apply h-12;
  @apply md:h-28;
  @apply rounded-md;
}

.skill-bar {
  @apply box-border;
}
.skill-container {
  @apply w-full;
  @apply bg-gray-300;
  @apply rounded-md;
}
.skills {
  background-color: var(--bg-color);
  width: var(--skill-width);
  @apply text-sm;
  @apply md:text-base;
  @apply lg:text-xl;
  @apply text-right;
  @apply text-white;
  @apply p-4;
  @apply rounded-l-md;
}
</style>
