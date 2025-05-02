<template>
    <div>
        <Navbar />

        <main class="text-center py-20 px-4">
            <h1 class="text-4xl font-bold text-gray-800 mb-4">Welcome to My Landing Page</h1>
            <p class="text-lg text-gray-600">This is where you can describe your product or service.</p>
        </main>

        <Footer />
    </div>
</template>

<script setup>
import Navbar from '../components/Navbar.vue'
import Footer from '../components/Footer.vue'
</script>