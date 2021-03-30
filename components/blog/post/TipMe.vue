<template>
  <div class="tip-me">
    <div class="top-row">
      <div class="call-to-action">
        Did you like what you read?
        <br />
        <a href="https://www.buymeacoffee.com/jstrother" target="_blank" class="coffee">
          Buy me a coffee! <img src="/img/icons/coffee.png" alt="Buy me a coffee!" />
        </a>
      </div>
    </div>
  </div>
</template>

<style scoped>
.tip-me {
  @apply flex flex-col flex-nowrap mt-4 lg:mt-auto;
}
.top-row {
  @apply flex flex-nowrap justify-around;
}
.call-to-action {
  @apply pt-4;
}
img {
  @apply m-0.5 ml-1.5;
}
.coffee {
  @apply flex flex-row flex-nowrap underline ml-4;
}
</style>
