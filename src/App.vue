<script setup>
import { ref } from 'vue';
import Navbar from './components/Navbar.vue'
import Home from './components/Home.vue'
import OurRecomendations from './components/OurRecomendations.vue'
import TrendingStays from './components/TrendingStays.vue'
import FAQs from './components/FAQs.vue';
import FooterLanding from './components/FooterLanding.vue';
import TabbarMobile from './components/TabbarMobile.vue';
import FormLogin from './components/FormLogin.vue';
import FormPasswordRecovery from './components/FormPasswordRecovery.vue';
import FormSignup from './components/FormSignup.vue';

// Referencias a los componentes de formularios
const loginForm = ref(null);
const passwordRecoveryForm = ref(null);
const registerForm = ref(null);

// Método para abrir el formulario de login
const openFormLogin = () => {
  loginForm.value.openForm();
};

// Método para abrir el formulario de recuperación de contraseña
const openPasswordRecoveryForm = () => {
  passwordRecoveryForm.value.openForm();
};

// Método para abrir el formulario de registro
const openRegisterForm = () => {
  registerForm.value.openForm();
};

</script>

<template>
  <!-- Navbar -->
  <Navbar @open-form-login="openFormLogin"/>

  <!-- Content -->
  <section class="w-full h-auto">
    <Home/>
    <OurRecomendations/>
    <TrendingStays/>
    <FAQs/>
  </section>
  <!-- Footer -->
  <FooterLanding/>
  <!-- Tabbar Mobile -->
  <TabbarMobile />
  <!-- Access Forms -->
  <FormLogin 
    ref="loginForm" 
    @open-password-recovery="openPasswordRecoveryForm"
    @open-register="openRegisterForm"
  />
  <FormPasswordRecovery ref="passwordRecoveryForm" />
  <FormSignup ref="registerForm" />
</template>
