<template>
  <div class="fixed top-0 left-0 right-0 z-50 px-4 sm:px-6 md:px-12 pt-4">
    <nav class="navbarColor rounded-2xl shadow-md border border-black px-4 sm:px-6 py-3 flex items-center justify-between relative">

      <div class="flex items-center gap-3">
        <img
          src="/imgGPLogo.png"
          alt="Logo Gabriel Paião"
          class="w-9 h-9 sm:w-10 sm:h-10 bg-black-500"
        />
        <div>
          <p class="font-bold text-white text-xs sm:text-sm leading-tight">Gabriel Paião</p>
          <p class="text-[9px] sm:text-[10px] text-white font-bold uppercase tracking-widest">
            Desenvolvedor de Software
          </p>
        </div>
      </div>

      <!-- Desktop links -->
      <ul class="hidden md:flex items-center gap-1">
        <li v-for="link in navLinks" :key="link.name">
          <a
          :href="`#${link.id}`"
          @click.prevent="scrollToSection(link.id)"
          class="relative group px-3 py-2 text-sm font-semibold text-white rounded-lg
          hover:text-violet-300 hover:bg-white/10 transition-colors duration-200
          after:absolute after:bottom-1 after:left-3 after:right-3 after:h-0.5
          after:bg-violet-500 after:rounded-full
          after:scale-x-0 hover:after:scale-x-100
          after:transition-transform after:duration-200 after:origin-left"
          >
          {{ link.name }}
          </a>
        </li>
      </ul>

      <!-- Mobile hamburger button -->
      <button
        class="md:hidden flex items-center justify-center w-9 h-9 text-white"
        @click="menuOpen = !menuOpen"
        aria-label="Abrir menu"
      >
        <svg v-if="!menuOpen" xmlns="http://www.w3.org/2000/svg" class="w-6 h-6" fill="none" viewBox="0 0 24 24" stroke="currentColor">
          <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M4 6h16M4 12h16M4 18h16" />
        </svg>
        <svg v-else xmlns="http://www.w3.org/2000/svg" class="w-6 h-6" fill="none" viewBox="0 0 24 24" stroke="currentColor">
          <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M6 18L18 6M6 6l12 12" />
        </svg>
      </button>

      <!-- Mobile dropdown menu -->
      <Transition name="fade">
        <ul
          v-if="menuOpen"
          class="absolute top-full left-0 right-0 mt-2 navbarColor rounded-2xl shadow-md border border-black flex flex-col p-3 gap-1 md:hidden"
        >
          <li v-for="link in navLinks" :key="link.name">
          <a
            :href="`#${link.id}`"
            @click.prevent="scrollToSection(link.id); menuOpen = false"
            class="block px-3 py-2 text-sm font-semibold text-white rounded-lg
            hover:text-violet-300 hover:bg-white/10 transition-colors duration-200"
            >
            {{ link.name }}
          </a>
          </li>
        </ul>
      </Transition>
    </nav>
  </div>
</template>

<script setup>
import { ref } from 'vue'

const menuOpen = ref(false)

const navLinks = [
  { name: 'Início',       id: 'home' },
  { name: 'Sobre',        id: 'about' },
  { name: 'Experiência',  id: 'experience' },
  { name: 'Projetos',     id: 'projects' },
  { name: 'Contratar',    id: 'hiring' },
]

function scrollToSection(id) {
  const el = document.getElementById(id)
  if (el) {
    const offset = 112 // adjust to match navbar height
    const top = el.getBoundingClientRect().top + window.scrollY - offset
    window.scrollTo({ top, behavior: 'smooth' })
  }
}
</script>

<style scoped>
.navbarColor {
  background-color: #1b1b1c;
}

.fade-enter-active,
.fade-leave-active {
  transition: opacity 0.15s ease, transform 0.15s ease;
}

.fade-enter-from,
.fade-leave-to {
  opacity: 0;
  transform: translateY(-4px);
}
</style>
