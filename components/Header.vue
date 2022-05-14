<template>
  <div class="py-4 border-b border-slate-900/10 lg:px-8 lg:border-0 dark:border-slate-300/10 mx-4 lg:mx-0">
    <div class="relative flex items-center">
      <!-- Menu for Mobile -->
      <div class="ml-0 -my-1 md:hidden">
        <button type="button" @click="menuNavBarToggle" class="text-slate-500 w-8 h-8 flex items-center justify-center hover:text-slate-600 dark:text-slate-400 dark:hover:text-slate-300">
          <span class="sr-only">Navigation</span>
          <svg
            class="h-8 w-8 fill-current text-black"
            fill="none" stroke-linecap="round"
            stroke-linejoin="round" stroke-width="2"
            viewBox="0 0 24 24" stroke="currentColor">
              <path d="M4 6h16M4 12h16M4 18h16"></path>
          </svg>
        </button>
      </div>
      <!-- Logo -->
      <nuxt-link to="/" class="ml-2 mr-3 flex-none w-[2.0625rem] md:w-auto">
        <span class="sr-only">Stock Festa</span>
        <svg viewBox="0 0 248 31" class="text-slate-900 dark:text-white w-auto h-5">
          <path fill-rule="evenodd" clip-rule="evenodd" d="M25.517 0C18.712 0 14.46 3.382 12.758 10.146c2.552-3.382 5.529-4.65 8.931-3.805 1.941.482 3.329 1.882 4.864 3.432 2.502 2.524 5.398 5.445 11.722 5.445 6.804 0 11.057-3.382 12.758-10.145-2.551 3.382-5.528 4.65-8.93 3.804-1.942-.482-3.33-1.882-4.865-3.431C34.736 2.92 31.841 0 25.517 0zM12.758 15.218C5.954 15.218 1.701 18.6 0 25.364c2.552-3.382 5.529-4.65 8.93-3.805 1.942.482 3.33 1.882 4.865 3.432 2.502 2.524 5.397 5.445 11.722 5.445 6.804 0 11.057-3.381 12.758-10.145-2.552 3.382-5.529 4.65-8.931 3.805-1.941-.483-3.329-1.883-4.864-3.432-2.502-2.524-5.398-5.446-11.722-5.446z" fill="#38bdf8"></path>
          <path fill-rule="evenodd" clip-rule="evenodd" d="M76.546 12.825h-4.453v8.567c0 2.285 1.508 2.249 4.453 2.106v3.463c-5.962.714-8.332-.928-8.332-5.569v-8.567H64.91V9.112h3.304V4.318l3.879-1.143v5.937h4.453v3.713zM93.52 9.112h3.878v17.849h-3.878v-2.57c-1.365 1.891-3.484 3.034-6.285 3.034-4.884 0-8.942-4.105-8.942-9.389 0-5.318 4.058-9.388 8.942-9.388 2.801 0 4.92 1.142 6.285 2.999V9.112zm-5.674 14.636c3.232 0 5.674-2.392 5.674-5.712s-2.442-5.711-5.674-5.711-5.674 2.392-5.674 5.711c0 3.32 2.442 5.712 5.674 5.712zm16.016-17.313c-1.364 0-2.477-1.142-2.477-2.463a2.475 2.475 0 012.477-2.463 2.475 2.475 0 012.478 2.463c0 1.32-1.113 2.463-2.478 2.463zm-1.939 20.526V9.112h3.879v17.849h-3.879zm8.368 0V.9h3.878v26.06h-3.878zm29.053-17.849h4.094l-5.638 17.849h-3.807l-3.735-12.03-3.771 12.03h-3.806l-5.639-17.849h4.094l3.484 12.315 3.771-12.315h3.699l3.734 12.315 3.52-12.315zm8.906-2.677c-1.365 0-2.478-1.142-2.478-2.463a2.475 2.475 0 012.478-2.463 2.475 2.475 0 012.478 2.463c0 1.32-1.113 2.463-2.478 2.463zm-1.939 20.526V9.112h3.878v17.849h-3.878zm17.812-18.313c4.022 0 6.895 2.713 6.895 7.354V26.96h-3.878V16.394c0-2.713-1.58-4.14-4.022-4.14-2.55 0-4.561 1.499-4.561 5.14v9.567h-3.879V9.112h3.879v2.285c1.185-1.856 3.124-2.749 5.566-2.749zm25.282-6.675h3.879V26.96h-3.879v-2.57c-1.364 1.892-3.483 3.034-6.284 3.034-4.884 0-8.942-4.105-8.942-9.389 0-5.318 4.058-9.388 8.942-9.388 2.801 0 4.92 1.142 6.284 2.999V1.973zm-5.674 21.775c3.232 0 5.674-2.392 5.674-5.712s-2.442-5.711-5.674-5.711-5.674 2.392-5.674 5.711c0 3.32 2.442 5.712 5.674 5.712zm22.553 3.677c-5.423 0-9.481-4.105-9.481-9.389 0-5.318 4.058-9.388 9.481-9.388 3.519 0 6.572 1.82 8.008 4.605l-3.34 1.928c-.79-1.678-2.549-2.749-4.704-2.749-3.16 0-5.566 2.392-5.566 5.604 0 3.213 2.406 5.605 5.566 5.605 2.155 0 3.914-1.107 4.776-2.749l3.34 1.892c-1.508 2.82-4.561 4.64-8.08 4.64zm14.472-13.387c0 3.249 9.661 1.285 9.661 7.89 0 3.57-3.125 5.497-7.003 5.497-3.591 0-6.177-1.607-7.326-4.177l3.34-1.927c.574 1.606 2.011 2.57 3.986 2.57 1.724 0 3.052-.571 3.052-2 0-3.176-9.66-1.391-9.66-7.781 0-3.356 2.909-5.462 6.572-5.462 2.945 0 5.387 1.357 6.644 3.713l-3.268 1.82c-.647-1.392-1.904-2.035-3.376-2.035-1.401 0-2.622.607-2.622 1.892zm16.556 0c0 3.249 9.66 1.285 9.66 7.89 0 3.57-3.124 5.497-7.003 5.497-3.591 0-6.176-1.607-7.326-4.177l3.34-1.927c.575 1.606 2.011 2.57 3.986 2.57 1.724 0 3.053-.571 3.053-2 0-3.176-9.66-1.391-9.66-7.781 0-3.356 2.908-5.462 6.572-5.462 2.944 0 5.386 1.357 6.643 3.713l-3.268 1.82c-.646-1.392-1.903-2.035-3.375-2.035-1.401 0-2.622.607-2.622 1.892z" fill="currentColor"></path>
        </svg>
      </nuxt-link>
      <!-- Menu for PC -->
      <div class="hidden md:block ml-1 text-slate-500 -my-1 flex items-center justify-center">
        <ul class="flex space-x-4 justify-center">
          <li><a href="#" class="active border-b-2 border-blue-500 pb-1">Home</a></li>
          <li><a href="#" class="">Services</a></li>
          <li><a href="#" class="">Features</a></li>
          <li><a href="#" class="">FAQ</a></li>
          <li><a href="#" class="">Contact</a></li>
        </ul>
      </div>
      <!-- Search -->
      <button type="button" class="ml-auto text-slate-500 w-8 h-8 -my-1 flex items-center justify-center hover:text-slate-600 dark:text-slate-400 dark:hover:text-slate-300">
        <span class="sr-only">Search</span>
        <svg width="24" height="24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" aria-hidden="true">
          <path d="m19 19-3.5-3.5"></path>
          <circle cx="11" cy="11" r="6"></circle>
        </svg>
      </button>
    </div>

    <!-- Dark Background Transition -->
    <transition
      enter-class="opacity-0"
      enter-active-class="ease-out transition-medium"
      enter-to-class="opacity-100"
      leave-class="opacity-100"
      leave-active-class="ease-out transition-medium"
      leave-to-class="opacity-0"
    >
      <div @keydown.esc="isOpen = false" v-show="isOpen" class="z-10 fixed inset-0 transition-opacity">
          <div @click="isOpen = false" class="absolute inset-0 bg-black opacity-50" tabindex="0"></div>
      </div>
    </transition>

    <!-- Drawer Menu -->
    <aside class="p-5 transform top-0 left-0 w-64 bg-white fixed h-full overflow-auto ease-in-out transition-all duration-300 z-30" :class="isOpen ? 'translate-x-0' : '-translate-x-full'">
      <div class="close">
        <button class="absolute top-0 right-0 mt-4 mr-4" @click="isOpen = false">
          <svg
            class="w-6 h-6"
            fill="none" stroke-linecap="round"
            stroke-linejoin="round" stroke-width="2"
            viewBox="0 0 24 24" stroke="currentColor">
            <path d="M6 18L18 6M6 6l12 12"></path>
          </svg>
        </button>
      </div>

      <!-- Logo in Menu -->
      <span @click="isOpen = false" class="flex w-full items-center p-4 border-b">
        <nuxt-link to="/">
          <Logo />
        </nuxt-link>
      </span>

      <ul class="divide-y font-sans">
        <li><a href="#" @click="isOpen = false" class="my-4 inline-block">Home</a></li>
        <li><a href="#" @click="isOpen = false" class="my-4 inline-block">Services</a></li>
        <li><a href="#" @click="isOpen = false" class="my-4 inline-block">Features</a></li>
        <li><a href="#" @click="isOpen = false" class="my-4 inline-block">FAQ</a></li>
        <li><a href="#" @click="isOpen = false" class="my-4 inline-block">Contact</a></li>
        <li><a href="#" @click="isOpen = false" class="my-8 w-full text-center font-semibold cta inline-block bg-blue-500 hover:bg-blue-600 px-3 py-2 rounded text-white">Sign Up</a></li>
      </ul>

      <div class="follow">
        <p class="italic font-sans text-sm">follow us:</p>
        <div class="social flex space-x-5 mt-4 ">
          <a href="#">
            <svg
              aria-hidden="true" focusable="false"
              data-prefix="fab" data-icon="twitter"
              class="h-5 w-5 fill-current text-gray-600" role="img"
              xmlns="http://www.w3.org/2000/svg" viewBox="0 0 512 512">
              <path fill="currentColor" d="M459.37 151.716c.325 4.548.325 9.097.325 13.645 0 138.72-105.583 298.558-298.558 298.558-59.452 0-114.68-17.219-161.137-47.106 8.447.974 16.568 1.299 25.34 1.299 49.055 0 94.213-16.568 130.274-44.832-46.132-.975-84.792-31.188-98.112-72.772 6.498.974 12.995 1.624 19.818 1.624 9.421 0 18.843-1.3 27.614-3.573-48.081-9.747-84.143-51.98-84.143-102.985v-1.299c13.969 7.797 30.214 12.67 47.431 13.319-28.264-18.843-46.781-51.005-46.781-87.391 0-19.492 5.197-37.36 14.294-52.954 51.655 63.675 129.3 105.258 216.365 109.807-1.624-7.797-2.599-15.918-2.599-24.04 0-57.828 46.782-104.934 104.934-104.934 30.213 0 57.502 12.67 76.67 33.137 23.715-4.548 46.456-13.32 66.599-25.34-7.798 24.366-24.366 44.833-46.132 57.827 21.117-2.273 41.584-8.122 60.426-16.243-14.292 20.791-32.161 39.308-52.628 54.253z"></path>
            </svg>
          </a>
          <a href="#">
            <svg
              aria-hidden="true" focusable="false"
              data-prefix="fab" data-icon="youtube"
              class="h-5 w-5 fill-current text-gray-600" role="img"
              xmlns="http://www.w3.org/2000/svg" viewBox="0 0 576 512">
              <path fill="currentColor" d="M549.655 124.083c-6.281-23.65-24.787-42.276-48.284-48.597C458.781 64 288 64 288 64S117.22 64 74.629 75.486c-23.497 6.322-42.003 24.947-48.284 48.597-11.412 42.867-11.412 132.305-11.412 132.305s0 89.438 11.412 132.305c6.281 23.65 24.787 41.5 48.284 47.821C117.22 448 288 448 288 448s170.78 0 213.371-11.486c23.497-6.321 42.003-24.171 48.284-47.821 11.412-42.867 11.412-132.305 11.412-132.305s0-89.438-11.412-132.305zm-317.51 213.508V175.185l142.739 81.205-142.739 81.201z"></path>
            </svg>
          </a>
        </div>
      </div>
    </aside>
  </div>
</template>

<script setup lang="ts">
import Logo from '@/components/Logo.vue'
import { ref } from 'vue'

const isOpen = ref<boolean | null>(false)

const menuNavBarToggle = () => {
  isOpen.value = !isOpen.value
}
</script>
