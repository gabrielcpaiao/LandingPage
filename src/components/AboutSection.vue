<script setup>
const skills = [
  'Java', 'Spring Boot', 'PHP', 'Laravel', 'Vue.js',
  'JavaScript', 'MySQL', 'PostgreSQL', 'Docker', 'Git'
]

const education = [
  { title: 'Pós-graduação em Tecnologia Java', institution: 'UTFPR', status: 'Concluído' },
  { title: 'Ciência da Computação', institution: 'UNIVEM', status: 'Concluído' },
  { title: 'Big Data no Agronegócio', institution: 'FATEC', status: 'Concluído' },
]
</script>

<template>
  <section id="about" class="py-20 px-4 sm:px-8 md:px-16 scroll-mt-28">
    <div class="max-w-5xl mx-auto grid md:grid-cols-5 gap-10">

      <div class="md:col-span-3">
        <p class="font-mono text-violet-400 text-xs uppercase tracking-widest mb-2">
          Apresentação
        </p>

        <h2 class="text-3xl font-bold mb-6">
          Quem sou eu
        </h2>

        <p class="text-gray-300 leading-relaxed mb-4">
          Hoje atuo na empresa <span class="text-white font-semibold">Altvia</span>, onde desenvolvo
          APIs REST em Java com Spring Boot, sistemas backend em PHP com Laravel e interfaces em
          Vue.js e Angular. Sou formado em Ciência da Computação pela UNIVEM e recentemente concluí
          uma pós-graduação em Tecnologia Java pela UTFPR.
        </p>

        <p class="text-gray-300 leading-relaxed">
          Antes disso, passei dois anos desenvolvendo sistemas para a
          <span class="text-white font-semibold">Secretaria de Tecnologia da
          Informação (STI) - Prefeitura de Marília/SP</span> e
          atuei como analista de dados na <span class="text-white font-semibold">Máquinas Agrícolas Jacto S.A</span>.
        </p>
      </div>

      <div class="md:col-span-2 space-y-8">

        <div>
          <h3 class="text-sm font-semibold uppercase tracking-widest text-gray-400 mb-3">
            Stack
          </h3>

          <div class="flex flex-wrap gap-2">
            <span
              v-for="skill in skills"
              :key="skill"
              class="font-mono text-xs px-3 py-1 rounded-full bg-violet-500/10 text-violet-300 border border-violet-500/30"
            >
              {{ skill }}
            </span>
          </div>
        </div>

        <div>
          <h3 class="text-sm font-semibold uppercase tracking-widest text-gray-400 mb-3">
            Formação
          </h3>

          <ul class="space-y-3">
            <li
              v-for="edu in education"
              :key="edu.title"
              class="flex items-start justify-between gap-3 text-sm"
            >
              <div>
                <p class="text-white font-medium">
                  {{ edu.title }}
                </p>

                <p class="text-gray-400">
                  {{ edu.institution }}
                </p>
              </div>

              <span
                :class="[
                  edu.status === 'Concluído'
                    ? 'text-green-400 border-green-400/30 bg-green-400/10'
                    : 'text-violet-300 border-violet-400/30 bg-violet-400/10',
                  'text-[10px] font-mono uppercase px-2 py-1 rounded-full border whitespace-nowrap'
                ]"
              >
                {{ edu.status }}
              </span>
            </li>
          </ul>
        </div>

      </div>
    </div>
  </section>
</template>

