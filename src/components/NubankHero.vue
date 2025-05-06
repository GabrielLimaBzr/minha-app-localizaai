<template>
    <div class="font-sans bg-gray-50 min-h-screen overflow-x-hidden">
        <!-- Hero Section com imagem -->
        <div class="relative">
            <img src="./../assets/pnc.png" alt="Background Nubank"
                class="w-full h-[50vh] sm:h-[70vh] lg:h-[80vh] object-cover rounded-b-3xl">

            <div class="absolute inset-0 bg-gradient-to-t from-purple-900/80 to-purple-700/50 rounded-b-3xl"></div>

            <div class="absolute inset-0 z-10 px-4 sm:px-8 lg:px-16 py-6 text-white flex flex-col">
                <!-- Header -->
                <div class="flex justify-between items-center">
                    <div class="flex items-center space-x-2">
                        <span class="text-2xl sm:text-3xl font-bold">NU</span>
                        <span class="text-xl sm:text-2xl">Nubank</span>
                    </div>
                    <button
                        class="bg-white px-4 py-2 rounded-full text-sm sm:text-base font-bold hover:bg-gray-100 transition duration-300 shadow-md">
                        Login
                    </button>
                </div>

                <div
                    class="absolute inset-0 z-10 px-4 sm:px-8 lg:px-16 py-6 text-white flex flex-col items-center justify-center text-center">
                    <div class="w-full max-w-md lg:max-w-2xl">
                        <h1 class="text-2xl sm:text-3xl lg:text-6xl font-bold mb-4 leading-tight">
                            <span
                                class="text-transparent bg-clip-text bg-gradient-to-r from-purple-200 to-white">N</span>
                            possibilidades de produtos feitos do jeito Nu
                        </h1>
                        <p class="text-lg sm:text-xl lg:text-2xl mb-6 opacity-90">
                            Peça seu Cartão de Crédito e sua Conta do Nubank
                        </p>

                        <div
                            class="bg-white/90 backdrop-blur-sm rounded-xl p-2 sm:p-4 flex flex-col sm:flex-row gap-2 shadow-lg">
                            <input v-model="cpf" type="text" placeholder="Digite seu CPF"
                                class="flex-grow px-4 py-3 lg:py-4 text-gray-800 outline-none rounded-lg focus:ring-2 focus:ring-purple-500"
                                @keyup.enter="handleContinue">
                            <button
                                class="bg-purple-600 hover:bg-purple-700 text-white px-6 py-3 lg:py-4 rounded-lg font-bold transition duration-300 transform hover:scale-105"
                                @click="handleContinue">
                                Continuar
                            </button>
                        </div>
                    </div>
                </div>
            </div>
        </div>

        <!-- Painel branco abaixo -->
        <div
            class="bg-white rounded-t-3xl -mt-6 sm:-mt-12 lg:-mt-16 relative z-20 px-4 sm:px-8 lg:px-16 py-8 shadow-lg max-w-screen-xl mx-auto">
            <h2 class="text-2xl sm:text-3xl lg:text-4xl font-bold text-gray-800 mb-6 lg:mb-10">
                Para cada momento, um Nubank diferente
            </h2>

            <div class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-4 gap-4 lg:gap-6">
                <!-- Card 1 -->
                <div
                    class="bg-gradient-to-br from-purple-50 to-gray-50 p-6 rounded-xl hover:shadow-md transition duration-300 cursor-pointer">
                    <div class="w-12 h-12 bg-purple-100 rounded-full flex items-center justify-center mb-4">
                        <svg class="w-6 h-6 text-purple-600" fill="currentColor" viewBox="0 0 20 20">
                            <path fill-rule="evenodd"
                                d="M4 4a2 2 0 00-2 2v4a2 2 0 002 2V6h10a2 2 0 00-2-2H4zm2 6a2 2 0 012-2h8a2 2 0 012 2v4a2 2 0 01-2 2H8a2 2 0 01-2-2v-4zm6 4a2 2 0 100-4 2 2 0 000 4z"
                                clip-rule="evenodd" />
                        </svg>
                    </div>
                    <h3 class="font-bold text-purple-900 text-lg lg:text-xl">Nubank Ultravioleta</h3>
                    <p class="text-gray-600 text-sm lg:text-base mt-2">O cartão premium para quem quer o melhor em
                        benefícios</p>
                </div>

                <!-- Card 2 -->
                <div
                    class="bg-gradient-to-br from-purple-50 to-gray-50 p-6 rounded-xl hover:shadow-md transition duration-300 cursor-pointer">
                    <div class="w-12 h-12 bg-purple-100 rounded-full flex items-center justify-center mb-4">
                        <svg class="w-6 h-6 text-purple-600" fill="currentColor" viewBox="0 0 20 20">
                            <path fill-rule="evenodd"
                                d="M10 2a4 4 0 00-4 4v1H5a1 1 0 00-.994.89l-1 9A1 1 0 004 18h12a1 1 0 00.994-1.11l-1-9A1 1 0 0015 7h-1V6a4 4 0 00-4-4zm2 5V6a2 2 0 10-4 0v1h4zm-6 3a1 1 0 112 0 1 1 0 01-2 0zm7-1a1 1 0 100 2 1 1 0 000-2z"
                                clip-rule="evenodd" />
                        </svg>
                    </div>
                    <h3 class="font-bold text-purple-900 text-lg lg:text-xl">Nu Empresas</h3>
                    <p class="text-gray-600 text-sm lg:text-base mt-2">Soluções financeiras completas para o seu negócio
                    </p>
                </div>

                <!-- Card 3 -->
                <div
                    class="bg-gradient-to-br from-purple-50 to-gray-50 p-6 rounded-xl hover:shadow-md transition duration-300 cursor-pointer">
                    <div class="w-12 h-12 bg-purple-100 rounded-full flex items-center justify-center mb-4">
                        <svg class="w-6 h-6 text-purple-600" fill="currentColor" viewBox="0 0 20 20">
                            <path d="M4 4a2 2 0 00-2 2v1h16V6a2 2 0 00-2-2H4z" />
                            <path fill-rule="evenodd"
                                d="M18 9H2v5a2 2 0 002 2h12a2 2 0 002-2V9zM4 13a1 1 0 011-1h1a1 1 0 110 2H5a1 1 0 01-1-1zm5-1a1 1 0 100 2h1a1 1 0 100-2H9z"
                                clip-rule="evenodd" />
                        </svg>
                    </div>
                    <h3 class="font-bold text-purple-900 text-lg lg:text-xl">Cartão de Crédito</h3>
                    <p class="text-gray-600 text-sm lg:text-base mt-2">Moderno, simples e sem tarifas. Peça o seu!</p>
                </div>

                <!-- Card 4 -->
                <div
                    class="bg-gradient-to-br from-purple-50 to-gray-50 p-6 rounded-xl hover:shadow-md transition duration-300 cursor-pointer">
                    <div class="w-12 h-12 bg-purple-100 rounded-full flex items-center justify-center mb-4">
                        <svg class="w-6 h-6 text-purple-600" fill="currentColor" viewBox="0 0 20 20">
                            <path fill-rule="evenodd"
                                d="M4 4a2 2 0 00-2 2v4a2 2 0 002 2V6h10a2 2 0 00-2-2H4zm2 6a2 2 0 012-2h8a2 2 0 012 2v4a2 2 0 01-2 2H8a2 2 0 01-2-2v-4zm6 4a2 2 0 100-4 2 2 0 000 4z"
                                clip-rule="evenodd" />
                        </svg>
                    </div>
                    <h3 class="font-bold text-purple-900 text-lg lg:text-xl">Conta Digital</h3>
                    <p class="text-gray-600 text-sm lg:text-base mt-2">A conta que vai levar você ao controle da sua
                        vida financeira</p>
                </div>
            </div>

            <h3 class="mt-5 font-bold text-purple-900 text-lg lg:text-xl">Comprovantes Gabriel Lima</h3>

            <!-- Footer Section -->
            <div
                class="mt-12 lg:mt-16 pt-6 border-t border-gray-200 flex flex-col sm:flex-row justify-between items-center">
                <div class="flex items-center space-x-4 mb-4 sm:mb-0">
                    <a href="#" class="text-sm text-gray-500 hover:text-purple-600 transition">Segurança</a>
                    <a href="#" class="text-sm text-gray-500 hover:text-purple-600 transition">Privacidade</a>
                    <a href="#" class="text-sm text-gray-500 hover:text-purple-600 transition">Ajuda</a>
                </div>
                <p class="text-xs sm:text-sm text-gray-500">
                    © 2023 Nubank. Todos os direitos reservados.
                </p>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    data() {
        return {
            cpf: ''
        }
    },
    methods: {
        handleContinue() {
            // Lógica para continuar
            console.log('CPF digitado:', this.cpf);
        }
    }
}
</script>

<style>
/* Adicionando animações suaves */
.min-h-screen {
    min-height: 100vh;
}

/* Efeito de gradiente animado no background do hero */
@keyframes gradientAnimation {
    0% {
        background-position: 0% 50%;
    }

    50% {
        background-position: 100% 50%;
    }

    100% {
        background-position: 0% 50%;
    }
}

.bg-gradient-animated {
    background-size: 200% 200%;
    animation: gradientAnimation 10s ease infinite;
}
</style>