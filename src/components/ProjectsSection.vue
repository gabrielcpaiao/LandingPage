<script setup>
const projects = [
  {
    title: 'Gerenciamento Financeiro',
    category: 'Portal Web · Administração Financeira',
    description:
      'Tranformando em Sistema Web as planilhas que usava para controle financeiro. Separando por abas: Visão geral da Renda/Salário, gastos com despesas fixa (boletos), cartão de crédito, gastos variáveis, quanto consegui investir e coluna de renda extra.',
  },
  {
    title: 'Aplicações Financeiras',
    category: 'Rotina de importação dados da XP',
    description:
      'Estudo do perfil do investidos e projeção de como ele irá se aposentar e como deve investir sua renda. ',
  },
  {
    title: 'Plataforma Imobiliária',
    category: 'Full Stack · Plataforma Web',
    description:
      'Atuação no desenvolvimento de uma plataforma para gestão e locação de imóveis, envolvendo APIs, regras de negócio e interfaces para o portal da aplicação.',
  },
  {
    title: 'Análise de Investimentos',
    category: 'Dados · Business Intelligence',
    description:
      'Solução criada para transformar dados de investimentos em indicadores e visualizações, permitindo acompanhar o desempenho dos aportes em relação a referências como CDI e SELIC.',
  },
]
</script>

<template>
  <section
    id="projects"
    class="py-20 px-4 sm:px-8 md:px-16 scroll-mt-28"
  >
    <div class="max-w-5xl mx-auto">

      <!-- Cabeçalho -->
      <div class="text-center mb-12">
        <p
          class="font-mono text-violet-400 text-xs uppercase tracking-widest mb-2"
        >
          Trabalho em destaque
        </p>

        <h2 class="text-3xl md:text-4xl font-bold mb-5">
          Projetos
        </h2>

        <p class="max-w-2xl mx-auto text-gray-400 text-sm md:text-base">
          Alguns projetos e soluções em que participei, envolvendo
          desenvolvimento de sistemas, APIs, interfaces e análise de dados.
        </p>
      </div>

      <!-- Projetos -->
      <div class="grid sm:grid-cols-2 gap-6">

        <article
          v-for="project in projects"
          :key="project.title"
          class="
            group
            relative
            overflow-hidden
            rounded-xl
            border
            border-neutral-700/70
            bg-neutral-800/50
            p-6
            transition-all
            duration-300
            ease-out
            hover:-translate-y-2
            hover:border-violet-500/60
            hover:bg-neutral-800/80
            hover:shadow-xl
            hover:shadow-violet-500/5
          "
        >

          <!-- Barra superior -->
          <div
            class="
              absolute
              top-0
              left-0
              right-0
              h-0.5
              origin-left
              scale-x-0
              bg-gradient-to-r
              from-violet-500
              to-fuchsia-500
              transition-transform
              duration-300
              group-hover:scale-x-100
            "
          ></div>

          <!-- Ícone -->
          <div
            class="
              flex
              h-11
              w-11
              items-center
              justify-center
              rounded-lg
              border
              border-violet-500/20
              bg-violet-500/10
              text-violet-400
              transition-all
              duration-300
              group-hover:scale-110
              group-hover:bg-violet-500/15
            "
          >
            <span class="font-mono text-lg">
              &lt;/&gt;
            </span>
          </div>

          <!-- Categoria -->
          <p
            class="
              mt-5
              text-[10px]
              font-mono
              uppercase
              tracking-widest
              text-violet-400
            "
          >
            {{ project.category }}
          </p>

          <!-- Título -->
          <h3
            class="
              mt-2
              text-xl
              font-bold
              text-white
              transition-colors
              duration-300
              group-hover:text-violet-300
            "
          >
            {{ project.title }}
          </h3>

          <!-- Descrição -->
          <p
            class="
              mt-3
              text-sm
              leading-6
              text-gray-400
            "
          >
            {{ project.description }}
          </p>

          <!-- Tags -->
          <div class="flex flex-wrap gap-2 mt-5">
            <span
              v-for="tag in project.tags"
              :key="tag"
              class="
                rounded-md
                border
                border-neutral-700
                bg-neutral-900/60
                px-2.5
                py-1
                text-[10px]
                font-mono
                uppercase
                tracking-wide
                text-gray-400
                transition-colors
                duration-300
                group-hover:border-violet-500/20
                group-hover:text-gray-300
              "
            >
              {{ tag }}
            </span>
          </div>

        </article>

      </div>

    </div>
  </section>
</template>
