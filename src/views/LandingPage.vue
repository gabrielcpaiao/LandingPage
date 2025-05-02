<template>
    <div>
        <Navbar />

        <main class="text-center py-20 px-4">

            <div class="hero bg-neutral-600 min-h-screen">
                <div class="hero-content flex-col lg:flex-row">
                    <img :src="myPhoto" alt="Profile picture"
                        class="max-w-sm rounded-lg shadow-2xl size-100 rounded-full" />
                    <div>
                        <h1 class="text-5xl font-bold">Olá, seja bem-vindo!</h1>
                        <p class="py-6">
                            Provident cupiditate voluptatem et in. Quaerat fugiat ut assumenda excepturi exercitationem
                            quasi. In deleniti eaque aut repudiandae et a id nisi.
                        </p>
                        <button class="btn btn-primary">Get Started</button>
                    </div>
                </div>
            </div>

            <hr>
            <br>

            <div>
                <h1>APRESENTAÇÃO</h1>
            </div>

            <hr>
            <br>
            <div>
                <h1>COLOAR AS EXPERIENCIAS PROFISSIONAIS E PROJETOS EXECUTADOS</h1>
            </div>
            <hr>
            <br>
            <div>
                <h1>IMPORTAR CURRICULO</h1>
            </div>
            <hr>
            <br>
            <div>
                <h1>ENTRAR EM CONTATO PARA GERAR LANDING PAGE</h1>
            </div>

        </main>

        <Footer />
    </div>
</template>

<script setup>
import Navbar from '../components/Navbar.vue'
import Footer from '../components/Footer.vue'
import myPhoto from '../assets/desenho.jpg';
</script>