<template>
  <section id="hiring" class="py-20 px-4 sm:px-8 md:px-16 bg-neutral-900 scroll-mt-28">
    <div class="max-w-5xl mx-auto">
      <p class="font-mono text-violet-400 text-xs uppercase tracking-widest mb-2 text-center">
        Vamos conversar
      </p>
      <h2 class="text-3xl font-bold mb-12 text-center">Vamos Trabalhar Juntos?</h2>

      <div class="grid md:grid-cols-2 gap-10 items-start">
        <!-- INFO COLUMN -->
        <div>
          <p class="text-gray-300 leading-relaxed mb-8">
            Tem um projeto em mente? Precisa de um desenvolvedor confiável para criar ou
            melhorar sua aplicação? Entre em contato e vamos conversar sobre como posso
            ajudar a transformar sua ideia em realidade.
          </p>

          <ul class="space-y-4">
            <li
              v-for="item in contactChannels"
              :key="item.label"
              class="flex items-start gap-4"
            >
              <span
                class="flex items-center justify-center w-13 h-13 rounded-full shrink-0 p-2"
              >
                <img
                  :src="item.icon"
                  :alt="item.label"
                  class="w-full h-full object-contain bg-gray-500 rounded-full"
                />
              </span>
              <div>
                <p class="text-xs font-mono uppercase tracking-widest text-gray-400">
                  {{ item.label }}
                </p>
                <a
                  :href="item.href"
                  target="_blank"
                  rel="noopener"
                  class="text-white font-medium hover:text-violet-300 transition-colors"
                >
                  {{ item.display }}
                </a>
              </div>
            </li>
          </ul>

          <!-- Quick CTA buttons -->
          <div class="flex flex-wrap gap-3 mt-8">
            <a :href="whatsappLink" target="_blank" rel="noopener" class="btn btn-primary">
              Chamar no WhatsApp
            </a>
            <a :href="`mailto:${email}`" class="btn btn-outline btn-primary">
              Enviar E-mail
            </a>
          </div>
        </div>

        <!-- FORM COLUMN -->
        <div class="bg-neutral-800/60 rounded-xl p-4 sm:p-8">
          <template v-if="!submitted">
            <h3 class="text-lg font-bold mb-4">Solicite um Orçamento</h3>

            <form class="space-y-4" @submit.prevent="handleSubmit">
              <div>
                <label for="name" class="block text-xs font-mono uppercase tracking-widest text-gray-400 mb-1">
                  Nome
                </label>
                <input
                  id="name"
                  v-model="form.name"
                  type="text"
                  placeholder="Seu nome"
                  required
                  class="w-full bg-neutral-900 border border-neutral-700 rounded-lg px-4 py-2.5 text-sm text-white placeholder-gray-500 focus:outline-none focus:border-violet-500 transition-colors"
                />
              </div>

              <div>
                <label for="email" class="block text-xs font-mono uppercase tracking-widest text-gray-400 mb-1">
                  E-mail
                </label>
                <input
                  id="email"
                  v-model="form.email"
                  type="email"
                  placeholder="Seu e-mail"
                  required
                  class="w-full bg-neutral-900 border border-neutral-700 rounded-lg px-4 py-2.5 text-sm text-white placeholder-gray-500 focus:outline-none focus:border-violet-500 transition-colors"
                />
              </div>

              <div>
                <label for="service" class="block text-xs font-mono uppercase tracking-widest text-gray-400 mb-1">
                  Serviço
                </label>
                <select
                  id="service"
                  v-model="form.service"
                  required
                  class="w-full bg-neutral-900 border border-neutral-700 rounded-lg px-4 py-2.5 text-sm text-white focus:outline-none focus:border-violet-500 transition-colors"
                >
                  <option value="" disabled>Tipo de serviço</option>
                  <option v-for="opt in serviceOptions" :key="opt.value" :value="opt.value">
                    {{ opt.label }}
                  </option>
                </select>
              </div>

              <div>
                <label for="message" class="block text-xs font-mono uppercase tracking-widest text-gray-400 mb-1">
                  Mensagem
                </label>
                <textarea
                  id="message"
                  v-model="form.message"
                  rows="4"
                  placeholder="Descreva seu projeto..."
                  required
                  class="w-full bg-neutral-900 border border-neutral-700 rounded-lg px-4 py-2.5 text-sm text-white placeholder-gray-500 focus:outline-none focus:border-violet-500 transition-colors resize-none"
                />
              </div>

              <button type="submit" class="btn btn-primary w-full">
                Enviar Mensagem
              </button>
            </form>
          </template>

          <!-- SUCCESS STATE -->
          <template v-else>
            <div class="flex flex-col items-center text-center py-8">
              <span class="flex items-center justify-center w-14 h-14 rounded-full bg-green-400/10 border border-green-400/30 text-green-400 mb-4">
                <svg xmlns="http://www.w3.org/2000/svg" class="w-7 h-7" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                  <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M9 12l2 2 4-4m6 2a9 9 0 11-18 0 9 9 0 0118 0z" />
                </svg>
              </span>
              <h3 class="text-lg font-bold mb-2">Mensagem Enviada!</h3>
              <p class="text-gray-300 mb-6">
                Seu cliente de e-mail deve abrir com a mensagem pronta. Se não abrir automaticamente,
                me chame direto no WhatsApp.
              </p>
              <button class="btn btn-outline btn-primary" @click="resetForm">
                Enviar outra mensagem
              </button>
            </div>
          </template>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
import { reactive, ref, computed } from 'vue'

const email = 'costapaiao@hotmail.com'
const whatsappNumber = '14996482811'

const form = reactive({
  name: '',
  email: '',
  service: '',
  message: '',
})

const submitted = ref(false)

const serviceOptions = [
  { value: 'backend', label: 'Desenvolvimento Backend (API)' },
  { value: 'frontend', label: 'Desenvolvimento Frontend' },
  { value: 'fullstack', label: 'Sistema Web Completo' },
  { value: 'dashboard', label: 'Dashboard / BI' },
  { value: 'other', label: 'Outro' },
]

const contactChannels = [
  {
    label: 'LinkedIn',
    display: 'linkedin.com/in/gabriel-paiao',
    href: 'https://linkedin.com/in/gabriel-paiao',
    icon: '/linkedin.png',
  },
  {
    label: 'E-mail',
    display: email,
    href: `mailto:${email}`,
    icon: '/mail.png',
  },
  {
    label: 'WhatsApp',
    display: '(14) 99648-2811',
    href: `https://wa.me/${whatsappNumber}`,
    icon: '/whatsapp.png',
  },
  {
    label: 'GitHub',
    display: 'github.com/gabrielcpaiao',
    href: 'https://github.com/gabrielcpaiao',
    icon: '/github.png',
  },
]

const whatsappLink = computed(() => {
  const text = encodeURIComponent(
    `Olá Gabriel! Meu nome é ${form.name || '...'} e gostaria de conversar sobre um projeto.`
  )
  return `https://wa.me/${whatsappNumber}?text=${text}`
})

function handleSubmit() {
  const subject = encodeURIComponent(
    `Orçamento: ${serviceOptions.find((s) => s.value === form.service)?.label || form.service}`
  )
  const body = encodeURIComponent(
    `Nome: ${form.name}\nE-mail: ${form.email}\n\nMensagem:\n${form.message}`
  )
  window.location.href = `mailto:${email}?subject=${subject}&body=${body}`
  submitted.value = true
}

function resetForm() {
  form.name = ''
  form.email = ''
  form.service = ''
  form.message = ''
  submitted.value = false
}
</script>
