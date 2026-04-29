<template>

  <div class="fixed top-0 left-0 right-0 z-50 px-12 pt-4 pb-4">
    <nav class="navbarColor rounded-2xl shadow-md border border-black px-6 py-3 flex items-center justify-between">

      <div class="flex items-center gap-3">

        <img
          src="@/assets/desenho.jpg"
          alt="Foto de Gabriel Paião"
          class="w-10 h-10 rounded-full object-cover ring-2 ring-black-300"
        />

        <div>
          <p class="font-bold text-white text-sm leading-tight">Gabriel Paião</p>
          <p class="text-[10px] text-white font-bold uppercase tracking-widest">Desenvolvedor de Software</p>
        </div>
      </div>

      <ul class="hidden md:flex items-center gap-1">

        <li v-for="link in navLinks" :key="link.name">

          <RouterLink
            :to="link.path"
            class="relative group px-3 py-2 text-sm font-medium text-gray-500 rounded-lg
                   hover:text-gray-900 hover:bg-gray-50 transition-colors duration-200
                   after:absolute after:bottom-1 after:left-3 after:right-3 after:h-0.5
                   after:bg-violet-500 after:rounded-full
                   after:scale-x-0 hover:after:scale-x-100
                   after:transition-transform after:duration-200 after:origin-left"
            active-class="text-violet-600 after:scale-x-100"
          >
            {{ link.name }}
          </RouterLink>
        </li>
      </ul>
    </nav>
  </div>
</template>

<script setup>

const navLinks = [
  { name: 'Início',        path: '/' },
  { name: 'Sobre',         path: '/sobre' },
  { name: 'Projetos',      path: '/projetos' },
  { name: 'Certificações', path: '/certificacoes' },
  { name: 'Contato',       path: '/contato' },
]
</script>

<style scoped>
.navbarColor {
  background-color: #1b1b1c;
}
</style>
