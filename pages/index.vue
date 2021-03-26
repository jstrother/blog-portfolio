<template>
  <main>
    <p class="animate-fadeIn3s">hello</p>
    <br />
    <p class="animate-fadeIn7s">my name is jim strother</p>
    <br />
    <p class="animate-fadeIn9s">
      i am a full-stack developer specializing in making the web a <span>greener</span> place
    </p>
  </main>
</template>

<script>
export default {};
</script>

<style scoped>
main {
  @apply flex-grow;
  @apply flex;
  @apply flex-col;
  @apply justify-center;
  @apply items-center;
  @apply text-center;
  @apply mb-auto;
  @apply p-14;
  @apply bg-gray-100;
}
span {
  @apply text-green-400;
}
</style>
