<script setup>
const projects = [
  {
    title: 'Censo PCD',
    description: 'Formulário público para mapeamento de pessoas com deficiência em Marília.',
    tags: ['PHP', 'MySQL', 'Acessibilidade'],
  },
  {
    title: 'Dashboard de Demanda Habitacional',
    description: 'Sistema de cadastro e visualização de dados para gestão de demandas habitacionais do município.',
    tags: ['PHP', 'Dashboard', 'Dados'],
  },
  {
    title: 'APIs REST — Altvia',
    description: 'APIs REST robustas em Java com Spring Boot para sistemas internos da empresa.',
    tags: ['Java', 'Spring Boot', 'REST'],
  },
]
</script>

<template>
  <section
    id="projects"
    class="py-20 px-4 sm:px-8 md:px-16 scroll-mt-28"
  >
    <div class="max-w-5xl mx-auto">

      <p
        class="font-mono text-violet-400 text-xs uppercase tracking-widest mb-2 text-center"
      >
        Trabalho em destaque
      </p>

      <h2 class="text-3xl font-bold mb-12 text-center">
        Projetos
      </h2>

      <div class="grid sm:grid-cols-2 lg:grid-cols-3 gap-6">

        <div
          v-for="project in projects"
          :key="project.title"
          class="bg-neutral-800/60 rounded-xl p-6 hover:-translate-y-1 transition-transform"
        >
          <h3 class="text-lg font-bold mb-2">
            {{ project.title }}
          </h3>

          <p class="text-sm text-gray-300 mb-4">
            {{ project.description }}
          </p>

          <div class="flex flex-wrap gap-2">
            <span
              v-for="tag in project.tags"
              :key="tag"
              class="font-mono text-[10px] uppercase px-2 py-1 rounded-full bg-violet-500/10 text-violet-300 border border-violet-500/30"
            >
              {{ tag }}
            </span>
          </div>
        </div>

      </div>

    </div>
  </section>
</template>

