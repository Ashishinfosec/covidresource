<template>
  <div>
    <div
      class="w-full bg-gray-100 dark:bg-gray-700 fixed sm:relative bottom-0 z-50"
    >
      <div class="container mx-auto flex justify-between items-center">
        <logo class="hidden sm:block" />
        <ul class="w-full sm:w-auto inline-flex justify-around">
          <li class="p-5">
            <menu-item to="/" :title="$t('appbar.home')">
              <svg
                class="w-6 h-6"
                fill="none"
                stroke="currentColor"
                viewBox="0 0 24 24"
                xmlns="http://www.w3.org/2000/svg"
              >
                <path
                  stroke-linecap="round"
                  stroke-linejoin="round"
                  stroke-width="2"
                  d="M3 12l2-2m0 0l7-7 7 7M5 10v10a1 1 0 001 1h3m10-11l2 2m-2-2v10a1 1 0 01-1 1h-3m-6 0a1 1 0 001-1v-4a1 1 0 011-1h2a1 1 0 011 1v4a1 1 0 001 1m-6 0h6"
                ></path>
              </svg>
            </menu-item>
          </li>
          <li class="p-5">
            <menu-item to="/resources" :title="$t('appbar.tiles')">
              <svg
                class="w-6 h-6"
                fill="none"
                stroke="currentColor"
                viewBox="0 0 24 24"
                xmlns="http://www.w3.org/2000/svg"
              >
                <path
                  stroke-linecap="round"
                  stroke-linejoin="round"
                  stroke-width="2"
                  d="M19 11H5m14 0a2 2 0 012 2v6a2 2 0 01-2 2H5a2 2 0 01-2-2v-6a2 2 0 012-2m14 0V9a2 2 0 00-2-2M5 11V9a2 2 0 012-2m0 0V5a2 2 0 012-2h6a2 2 0 012 2v2M7 7h10"
                ></path>
              </svg>
            </menu-item>
          </li>
          <li class="p-5">
            <menu-item to="/add" :title="$t('appbar.add')">
              <svg
                class="w-6 h-6"
                fill="none"
                stroke="currentColor"
                viewBox="0 0 24 24"
                xmlns="http://www.w3.org/2000/svg"
              >
                <path
                  stroke-linecap="round"
                  stroke-linejoin="round"
                  stroke-width="2"
                  d="M12 9v3m0 0v3m0-3h3m-3 0H9m12 0a9 9 0 11-18 0 9 9 0 0118 0z"
                ></path>
              </svg>
            </menu-item>
          </li>
          <li class="p-5">
            <button @click="toggleDrawer" class="focus:outline-none">
              <icon-menu :isOpened="drawer" />
            </button>
          </li>
        </ul>
      </div>
    </div>
    <transition name="fade">
      <offsite-nav v-if="drawer" />
    </transition>
  </div>
</template>

<script>
import ColorSwitcher from "../Atoms/ColorSwitcher.vue";
import IconMenu from "../Atoms/IconMenu.vue";
import MenuItem from "../Atoms/MenuItem.vue";
import OffsiteNav from "../Molecules/OffsiteNav.vue";
import Logo from "./../Atoms/Logo";
export default {
  components: { Logo, ColorSwitcher, IconMenu, OffsiteNav, MenuItem },
  data() {
    return {
      drawer: false
    };
  },
  methods: {
    toggleDrawer() {
      this.drawer = !this.drawer;
    }
  }
};
</script>

<style></style>
