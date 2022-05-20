<template>
  <header>
    <Menu>
      <MenuButton><MenuIcon class="h-8 w-8 stroke-blue-500" /><span class="sr-only">Menu</span></MenuButton>
      <MenuItems class="flex flex-col">
        <MenuItem v-slot="{ active }">
          <a :class="{ 'bg-blue-500 text-white': active }" href="/account-settings"> Account settings </a>
        </MenuItem>
        <MenuItem v-slot="{ active }">
          <RouterLink to="/" class="text-blue-600 underline" :class="{ 'bg-blue-500 text-white': active }">Accueil</RouterLink>
        </MenuItem>
        <MenuItem v-slot="{ active }">
          <RouterLink to="/non-existant" :class="{ 'bg-blue-500 text-white': active }" class="text-blue-600 underline">Autre </RouterLink>
        </MenuItem>
      </MenuItems>
    </Menu>
  </header>

  <RouterView />
</template>

<script>
import { Menu, MenuButton, MenuItems, MenuItem } from "@headlessui/vue";
import { MenuIcon } from "@heroicons/vue/outline";
export default {
  components: { Menu, MenuButton, MenuItems, MenuItem, MenuIcon },
};
</script>
