<template>
  <Menu as="div" class="relative inline-block text-left">
    <div>
      <MenuButton
        v-slot="{ open }"
        class="inline-flex justify-center w-full px-4 py-2 font-medium rounded-md select-none text-light-text dark:text-dark-text bg-light-content dark:bg-dark-content hover:bg-light-highlight dark:hover:bg-dark-highlight focus-brand"
      >
        <div class="flex items-center space-x-2 text-sm">
          <Icon name="bi:globe" />
          <p class="uppercase sr-only lg:not-sr-only">{{ $i18n.locale }}</p>
          <p></p>
          <Icon
            name="bi:chevron-down"
            :class="open ? 'rotate-180 transform' : ''"
          />
        </div>
      </MenuButton>
    </div>

    <transition
      enter-active-class="transition duration-100 ease-out"
      enter-from-class="transform scale-95 opacity-0"
      enter-to-class="transform scale-100 opacity-100"
      leave-active-class="transition duration-75 ease-in"
      leave-from-class="transform scale-100 opacity-100"
      leave-to-class="transform scale-95 opacity-0"
    >
      <MenuItems
        class="absolute right-0 mt-2 origin-top-right border divide-y rounded-md shadow-lg bg-light-content dark:bg-dark-content ring-1 ring-black ring-opacity-5 focus:outline-none border-light-text dark:border-dark-text"
      >
        <ul class="px-2 py-2">
          <NuxtLink
            v-for="locale in availableLocales"
            :key="locale.code"
            :to="switchLocalePath(locale.code)"
          >
            <MenuItem v-slot="{ active }">
              <li
                :class="[
                  active
                    ? 'bg-light-cta-orange dark:bg-dark-cta-orange text-light-content dark:text-dark-content'
                    : 'text-light-text dark:text-dark-text',
                  'w-28 group flex items-center rounded-md pl-4 pr-2 py-2 text-sm',
                ]"
              >
                {{ locale.name }}
              </li>
            </MenuItem>
          </NuxtLink>
        </ul>
      </MenuItems>
    </transition>
  </Menu>
</template>

<script setup>
import { Menu, MenuButton, MenuItem, MenuItems } from "@headlessui/vue";
const { locale, locales } = useI18n();
const switchLocalePath = useSwitchLocalePath();
const availableLocales = computed(() => {
  return locales.value.filter((i) => i.code !== locale.value);
});
</script>
