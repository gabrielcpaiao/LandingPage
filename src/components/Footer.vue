<template>
  <footer class="border-t border-white/10 py-10">
    <div class="max-w-5xl mx-auto px-4 sm:px-8 md:px-16">
      <div
        class="flex flex-col sm:flex-row items-center
               justify-between gap-6 text-center sm:text-left"
      >
        <!-- 1. Logo -->
        <img
          src="/imgGPLogo.png"
          alt="Logo Gabriel Paião"
          class="w-10 h-10"
        />

        <!-- 2. Copyright (Middle) -->
        <p class="text-sm text-gray-500">
          Desenvolvido por Gabriel Paião © {{ currentYear }}
        </p>

        <!-- 3. Social links -->
        <div class="flex items-center gap-3">
          <!-- LinkedIn -->
          <a
            href="https://linkedin.com/in/gabriel-paiao"
            target="_blank"
            rel="noopener noreferrer"
            aria-label="LinkedIn"
            class="w-10 h-10 rounded-full
               border border-white/10
               flex items-center justify-center
               hover:-translate-y-1
               transition-all duration-200"
          >
            <img
              src="/linkedin.png"
              alt="LinkedIn"
              class="w-full h-full object-contain"
            />
          </a>

          <!-- Email -->
          <a
            href="mailto:costapaiao@hotmail.com"
            aria-label="Email"
            class="w-10 h-10 rounded-full
               border border-white/10
               flex items-center justify-center
               hover:-translate-y-1
               transition-all duration-200"
          >
            <img
              src="/mail.png"
              alt="Email"
              class="w-full h-full object-contain"
            />
          </a>

          <!-- WhatsApp -->
          <a
            href="https://wa.me/5514996482811"
            target="_blank"
            rel="noopener noreferrer"
            aria-label="WhatsApp"
            class="w-10 h-10 rounded-full
               border border-white/10
               flex items-center justify-center
               hover:-translate-y-1
               transition-all duration-200"
          >
            <img
              src="/whatsapp.png"
              alt="WhatsApp"
              class="w-full h-full object-contain"
            />
          </a>

          <!-- GitHub -->
          <a
            href="https://github.com/gabrielcpaiao"
            target="_blank"
            rel="noopener noreferrer"
            aria-label="GitHub"
            class="w-10 h-10 rounded-full
               border border-black/10
               flex items-center justify-center
               hover:-translate-y-1
               bg-gray-100
               transition-all duration-200"
          >
            <img
              src="/github.png"
              alt="GitHub"
              class="w-full h-full object-contain"
            />
          </a>
        </div>
      </div>
    </div>
  </footer>
</template>

<script setup>
const currentYear = new Date().getFullYear()
</script>
