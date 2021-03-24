<template>
  <div class="tip-me">
    <div class="top-row">
      <div class="call-to-action">
        Did you like what you read?
        <br />
        Throw a little Nano my way!
      </div>
      <img
        src="/img/blog/nano-wallet-qr-code.jpg"
        alt="nano_3e9zew3ccdqqmigmb4iecxbgkp4ff4bmmfdcb7yo45tt8egtc7ghxfqj8ct1"
      />
    </div>
    <p>
      Nano Wallet:
      <span>nano_3e9zew3ccdqqmigmb4iecxbgkp4ff4bmmfdcb7yo45tt8egtc7ghxfqj8ct1</span>
    </p>
  </div>
</template>

<style scoped>
.tip-me {
  @apply flex;
  @apply flex-col;
  @apply flex-nowrap;
  @apply md:mt-4;
}
.top-row {
  @apply flex;
  @apply flex-nowrap;
  @apply justify-around;
}
.call-to-action {
  @apply pt-4;
}
img {
  @apply w-20;
  @apply h-20;
  @apply m-0.5;
}
p {
  @apply text-xs;
  @apply text-gray-500;
}
span {
  @apply select-all;
}
</style>
