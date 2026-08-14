<script setup>
const experiences = [
  {
    role: 'Desenvolvedor de Software (Full Stack)',
    company: 'Altvia',
    period: 'Set 2024 — Atual',
    description:
      'Desenvolvimento e manutenção de aplicações web e APIs REST para diferentes soluções de negócio, atuando tanto no backend quanto no frontend.',
    technologies: ['Java', 'Spring Boot', 'PHP', 'Laravel', 'Vue.js', 'Angular', 'MySQL', 'PostgreSQL', 'ASP.NET C#', 'Git'],
    highlights: [
      'Desenvolvi APIs REST em Java com Spring Boot para plataformas de locação de imóveis, incluindo integrações com sistemas legados.',
      'Construí e mantive sistemas backend em PHP com Laravel para aplicações financeiras, com rotinas de importação de dados da XP.',
      'Criei interfaces frontend responsivas com Vue.js e Angular, focando em usabilidade e performance.',
      'Participei da manutenção e evolução de uma plataforma legada de treinamentos em ASP.NET C#, implementando novas funcionalidades.',
    ],
  },
  {
    role: 'Analista de Dados — Estágio',
    company: 'Máquinas Agrícolas Jacto S.A. — Pompéia, SP',
    period: 'Nov 2023 — Jul 2024',
    description:
      'Desenvolvimento de uma solução de análise de investimentos e fundos imobiliários, transformando dados brutos em indicadores e visualizações para apoio à tomada de decisão.',
    technologies: ['Python', 'Power BI', 'Excel', 'Dados Públicos'],
    highlights: [
      'Estruturei KPIs e criei dashboards interativos no Power BI para análise de investimentos em fundos imobiliários.',
      'Automatizei a importação e limpeza de dados públicos (CVM e IPEADATA) utilizando Python, substituindo processos manuais.',
      'Desenvolvi indicadores visuais e relatórios estratégicos para apoiar a tomada de decisão da gestão de investimentos.',
    ],
  },
  {
    role: 'Desenvolvedor Web Full Stack — Estágio',
    company: 'Secretaria de Tecnologia da Informação (STI) — Prefeitura de Marília, SP',
    period: 'Nov 2021 — Nov 2023',
    description:
      'Desenvolvimento e manutenção de sistemas web para diferentes áreas da administração pública, contribuindo para a digitalização e organização de processos.',
    technologies: ['PHP', 'Laravel', 'JavaScript', 'MySQL', 'Git'],
    highlights: [
      'Desenvolvi o formulário digital do Censo PCD, ampliando a acessibilidade e coleta de dados de pessoas com deficiência cujo objetivo era captar dados para criação de políticas públicas.',
      'Colaborei na construção do novo sistema de Intranet municipal, modernizando a comunicação interna.',
      'Criei o sistema de cadastro de demanda habitacional, com formulário e dashboard para gestão de dados.',
    ],
  },
]
</script>

<template>
  <section
    id="experience"
    class="py-20 px-4 sm:px-8 md:px-16 bg-neutral-900 scroll-mt-28"
  >
    <div class="max-w-4xl mx-auto">

      <!-- Cabeçalho -->
      <div class="text-center mb-12">
        <p
          class="font-mono text-violet-400 text-xs uppercase tracking-widest mb-2"
        >
          Trajetória
        </p>

        <h2 class="text-3xl md:text-4xl font-bold mb-5">
          Experiência Profissional
        </h2>

        <p class="max-w-2xl mx-auto text-gray-400 text-sm md:text-base">
          Experiência no desenvolvimento de sistemas web, APIs e soluções
          orientadas a dados, atuando em diferentes contextos e tecnologias.
        </p>

        <div class="mt-7">
          <a
            href="/GabrielPaiaoDesenvolvedorSoftware.pdf"
            target="_blank"
            rel="noopener noreferrer"
            class="btn btn-primary"
          >
            Baixar Currículo
          </a>
        </div>
      </div>

      <!-- Timeline -->
      <ul class="relative ml-3 space-y-10">

        <!-- Linha -->
        <div
          class="absolute left-0 top-0 bottom-0 w-px bg-gradient-to-b from-violet-500/60 via-violet-500/20 to-transparent"
        ></div>

        <li
          v-for="job in experiences"
          :key="`${job.company}-${job.period}`"
          class="relative ml-7 group"
        >
          <!-- Ponto da timeline -->
          <span
            class="
              absolute
              -left-[35px]
              top-6
              w-4
              h-4
              rounded-full
              bg-violet-500
              ring-4
              ring-neutral-900
              transition-all
              duration-300
              group-hover:scale-125
              group-hover:ring-violet-500/20
            "
          ></span>

          <!-- Card -->
          <article
            class="
              relative
              rounded-xl
              border
              border-neutral-700/70
              bg-neutral-800/50
              p-5
              sm:p-6
              transition-all
              duration-300
              ease-out
              hover:-translate-y-1
              hover:translate-x-1
              hover:border-violet-500/60
              hover:bg-neutral-800/80
              hover:shadow-lg
              hover:shadow-violet-500/5
            "
          >
            <!-- Período -->
            <span
              class="
                inline-block
                mb-3
                rounded-full
                border
                border-violet-500/20
                bg-violet-500/10
                px-3
                py-1
                text-xs
                font-mono
                uppercase
                tracking-wide
                text-violet-400
              "
            >
              {{ job.period }}
            </span>

            <!-- Cargo -->
            <h3
              class="
                text-lg
                sm:text-xl
                font-bold
                text-white
                transition-colors
                duration-300
                group-hover:text-violet-300
              "
            >
              {{ job.role }}
            </h3>

            <!-- Empresa -->
            <p class="mt-1 text-sm font-medium text-violet-400">
              {{ job.company }}
            </p>

            <!-- Descrição -->
            <p
              class="
                mt-4
                text-sm
                leading-6
                text-gray-400
              "
            >
              {{ job.description }}
            </p>

            <!-- Highlights -->
            <ul
              class="
                mt-4
                space-y-2
                text-sm
                leading-6
                text-gray-300
              "
            >
              <li
                v-for="(item, i) in job.highlights"
                :key="i"
                class="flex gap-2"
              >
                <span class="mt-2 h-1.5 w-1.5 shrink-0 rounded-full bg-violet-400"></span>

                <span>{{ item }}</span>
              </li>
            </ul>

            <!-- Tecnologias -->
            <div class="flex flex-wrap gap-2 mt-5 pt-4 border-t border-neutral-700/50">
              <span
                v-for="technology in job.technologies"
                :key="technology"
                class="
                  rounded-md
                  bg-neutral-900/70
                  px-2.5
                  py-1
                  text-xs
                  font-mono
                  text-gray-400
                  transition-colors
                  duration-300
                  group-hover:text-gray-300
                "
              >
                {{ technology }}
              </span>
            </div>
          </article>
        </li>

      </ul>
    </div>
  </section>
</template>
