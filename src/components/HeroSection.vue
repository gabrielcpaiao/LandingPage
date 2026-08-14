<template>
  <section id="home" class="hero min-h-[50vh] bg-neutral-900 px-4 scroll-mt-28">
    <div class="hero-content flex-col lg:flex-row gap-10 max-w-5xl text-center lg:text-left">
      <img
        :src="photo"
        :alt="photoAlt"
        class="rounded-full shadow-2xl w-40 h-40 sm:w-56 sm:h-56 lg:w-72 lg:h-72 object-cover ring-4 ring-white-500/30"
      />
      <div>
        <p class="font-mono text-violet-400 text-sm tracking-widest uppercase mb-2">
          {{ badge }}
        </p>
        <h1 class="text-4xl sm:text-5xl font-bold leading-tight">{{ title }}</h1>
        <p class="py-6 text-gray-300 max-w-xl">
          {{ description }}
        </p>
        <div class="flex flex-wrap gap-3 justify-center lg:justify-start">
          <a
            :href="primaryButton.link"
            @click.prevent="handlePrimaryClick"
            class="btn btn-primary"
          >
            {{ primaryButton.text }}
          </a>
          <a
            :href="secondaryButton.link"
            :download="secondaryButton.download"
            rel="noopener noreferrer"
            class="btn btn-outline btn-primary"
            target="_blank"
          >
            {{ secondaryButton.text }}
          </a>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
import { scrollToSection } from '../Utils/scrollToSection'

const props = defineProps({
  photo: {
    type: String,
    required: true
  },
  photoAlt: {
    type: String,
    default: 'Foto de perfil'
  },
  badge: {
    type: String,
    default: 'Desenvolvedor de Software'
  },
  title: {
    type: String,
    default: 'Seja bem-vindo!'
  },
  description: {
    type: String,
    default: 'Esta Landing Page foi criada para apresentar minhas experiências acadêmicas e profissionais e, principalmente, conectar-me com empresas e profissionais que buscam soluções de software. Além da minha atuação profissional, também trabalho como Freelancer, desenvolvendo Landing Pages, sistemas web e soluções personalizadas. Está em busca de um Desenvolvedor de Software para o seu negócio? Entre em contato e vamos conversar sobre o seu projeto.'
  },
  primaryButton: {
    type: Object,
    default: () => ({
      text: 'Ver Projetos',
      link: '#projects'
    })
  },
  secondaryButton: {
    type: Object,
    default: () => ({
      text: 'Baixar Currículo',
      link: '/curriculo-gabriel-paiao.pdf',
      download: true
    })
  }
})

function handlePrimaryClick() {
  const id = props.primaryButton.link.replace('#', '')

  scrollToSection(id)
}
</script>

<style scoped>

</style>
