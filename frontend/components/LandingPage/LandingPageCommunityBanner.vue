<template>
  <div
    class="flex flex-col w-full py-4 space-y-1 xl:py-6 sm:space-y-2 xl:space-y-4 bg-light-highlight dark:bg-dark-highlight text-light-special-text dark:text-dark-special-text"
  >
    <div
      class="flex justify-center space-x-12 text-lg sm:space-x-8 xl:space-x-12 xl:text-xl"
    >
      <a
        href="https://github.com/activist-org/activist"
        class="flex items-center space-x-3 hover:text-light-text dark:hover:text-dark-text focus-brand"
      >
        <Icon name="bi:github" size="1em" />
        <p class="sr-only sm:not-sr-only">GitHub</p>
      </a>
      <a
        href="https://twitter.com/activist_org"
        class="flex items-center space-x-3 hover:text-light-text dark:hover:text-dark-text focus-brand"
      >
        <Icon name="bi:twitter" size="1em" />
        <p class="sr-only sm:not-sr-only">Twitter</p>
      </a>
      <a
        href="https://instagram.com/activist_org"
        class="flex items-center space-x-3 hover:text-light-text dark:hover:text-dark-text focus-brand"
      >
        <Icon name="bi:instagram" size="1em" />
        <p class="sr-only sm:not-sr-only">Instagram</p>
      </a>
    </div>
  </div>
</template>

<script setup>
const localePath = useLocalePath();
</script>
