<template>
  <div class="bg-neutral-950 text-white min-h-screen">
    <Navbar />

    <main class="pt-25">

      <!-- HERO Component/HOME -->
      <HeroSection
        :photo="myPhoto"
        photo-alt="Foto de Gabriel Paião"
        :primary-button="{
          text: 'Contratar',
          link: '#hiring'
        }"
        :secondary-button="{
          text: 'Baixar Currículo',
          link: '/GabrielPaiaoDesenvolvedorSoftware.pdf',
        }"
      />

      <!-- ABOUT -->
      <AboutSection />

      <!-- EXPERIENCE -->
      <ExperienceSection />

      <!-- PROJECTS -->
      <ProjectsSection />

      <!-- HIRING -->
      <HireSection />

    </main>

    <Footer />
  </div>
</template>

<script setup>
import Navbar from '../components/Navbar.vue'
import HeroSection from '../components/HeroSection.vue'
import AboutSection from '../components/AboutSection.vue'
import ExperienceSection from '../components/ExperienceSection.vue'
import HireSection from '../components/HireSection.vue'
import Footer from '../components/Footer.vue'
import myPhoto from '../assets/GabrielPaiaoFoto.jpeg'
import ProjectsSection from '../components/ProjectsSection.vue'

</script>
