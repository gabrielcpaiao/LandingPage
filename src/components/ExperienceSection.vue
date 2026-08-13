<script setup>
const experiences = [
  {
    role: 'Desenvolvedor de Software (Full Stack)',
    company: 'Altvia',
    period: 'Set 2024 — Atual',
    bullets: [
      'Desenvolvo APIs REST em Java com Spring Boot.',
      'Construo sistemas backend em PHP com Laravel.',
      'Crio interfaces frontend com Vue.js e Angular.',
    ],
  },
  {
    role: 'Analista de Dados — Estágio',
    company: 'Máquinas Agrícolas Jacto S.A. — Pompéia, SP',
    period: 'Nov 2023 — Jul 2024',
    bullets: [
      'Apoiei o projeto de KPIs de investimentos em fundos mobiliários.',
      'Criei indicadores visuais para análise e visualização de dados.',
      'Desenvolvi páginas no SharePoint.',
    ],
  },
  {
    role: 'Desenvolvedor Web Full Stack — Estágio',
    company: 'Secretaria de Tecnologia da Informação (STI) — Prefeitura de Marília, SP',
    period: 'Nov 2021 — Nov 2023',
    bullets: [
      'Criei o formulário do Censo PCD, voltado a pessoas com deficiência.',
      'Contribuí para o novo sistema de Intranet da Prefeitura de Marília.',
      'Desenvolvi o cadastro de demanda habitacional (formulário e dashboard).',
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

      <p
        class="font-mono text-violet-400 text-xs uppercase tracking-widest mb-2 text-center"
      >
        Trajetória
      </p>

      <h2 class="text-3xl font-bold mb-5 text-center">
        Experiência Profissional
      </h2>

      <div class="max-w-4xl mx-auto pb-8 text-center">
        <a
          href="/GabrielPaiaoDesenvolvedorSoftware.pdf"
          target="_blank"
          class="btn btn-primary"
        >
          Baixar Currículo (PDF)
        </a>
      </div>

      <ul class="relative border-l-2 border-violet-500/30 ml-3 space-y-10">

        <li
          v-for="job in experiences"
          :key="job.company"
          class="ml-6 relative"
        >
          <span
            class="absolute -left-[31px] top-1 w-4 h-4 bg-violet-500 rounded-full ring-4 ring-neutral-900"
          ></span>

          <div
            class="bg-neutral-800/60 rounded-xl p-5 hover:-translate-y-0.5 transition-transform"
          >
            <div
              class="flex flex-col sm:flex-row sm:items-center sm:justify-between gap-1 mb-2"
            >
              <h3 class="text-lg font-bold">
                {{ job.role }}
              </h3>

              <span
                class="text-xs font-mono uppercase tracking-wide text-violet-400"
              >
                {{ job.period }}
              </span>
            </div>

            <p class="text-sm text-gray-400 mb-3">
              {{ job.company }}
            </p>

            <ul class="list-disc list-inside text-sm text-gray-300 space-y-1">
              <li
                v-for="(item, i) in job.bullets"
                :key="i"
              >
                {{ item }}
              </li>
            </ul>
          </div>
        </li>

      </ul>
    </div>

  </section>
</template>

