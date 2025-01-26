<script setup>
    import { ref } from 'vue';

    // Emitir eventos al componente padre
    const emit = defineEmits(['open-password-recovery', 'open-register']);

    // Estados reactivos
    const email = ref('');
    const password = ref('');
    const message = ref('');
    const success = ref(false);
    const isVisible = ref(false);

    // Simular acceso a una sección restringida
    const simulateRestrictedAccess = () => {
        // Redirigir a la página de inicio        
        window.location.href = '/dashboard';  
    }

    // Método para iniciar sesión
    const login = async () => {
        // Validación campos
        if (!email.value) {
            message.value = 'Por favor, introduce tu email.';
            success.value = false;
            return;
        }

        if (!password.value) {
            message.value = 'Por favor, introduce tu contraseña.';
            success.value = false;
            return;
        }

        try {
            const response = await fetch('https://reqres.in/api/login', {
                method: 'POST',
                headers: {
                    'Content-Type': 'application/json',
                },
                body: JSON.stringify({
                    email: email.value,
                    password: password.value,                    
                }),                
            });

            const data = await response.json();
            if (response.ok) {
                // Se almacena el token en el localStorage
                localStorage.setItem('authToken', data.token);
                message.value = 'Login exitoso!';
                success.value = true;
                // Se simula acceso a una sección restringida
                simulateRestrictedAccess();
            } else {
                if (data.error === 'user not found') {
                    message.value = 'Usuario no encontrado.';
                } else {
                    message.value = data.error || 'Error en el login';
                    success.value = false;
                }
            }
        } catch (error) {
            message.value = 'Error en la conexión';
            success.value = false;
        }
    };

    // Método para abrir el formulario de recuperación de contraseña
    const openPasswordRecoveryForm = () => {
        closeForm(); // Cierra el formulario de login
        emit('open-password-recovery'); // Emite un evento para abrir el formulario de recuperación
    };

    // Método para abrir el formulario de registro
    const openRegisterForm = () => {
        closeForm(); // Cierra el formulario de login
        emit('open-register'); // Emite un evento para abrir el formulario de registro
    };

    // Método para abrir el formulario
    const openForm = () => {
        isVisible.value = true;
    };

    // Método para cerrar el formulario
    const closeForm = () => {
        isVisible.value = false;
        email.value = '';
        password.value = '';
        message.value = '';
        success.value = false;
    };

    // Exponer métodos al padre
    defineExpose({ openForm, closeForm });
</script>

<template>
    <div
        v-if="isVisible"
        style="background-color: rgba(0, 0, 0, 0.5)"
        class="fixed inset-0 flex justify-end transition-opacity duration-300"
        @click="closeForm"
    >
        <div
            class="mt-10 bg-white w-96 h-full shadow-lg transform transition-transform duration-300"
            :class="{'translate-x-0': isVisible, 'translate-x-full': !isVisible}"
            @click.stop
        >
            <!-- Botón de cierre -->
            <div class="border-slate-300 border-b-1 h-14 mx-6">
                <button
                    @click="closeForm"
                    class="absolute top-4 right-4 text-gray-500 hover:text-tertiary focus:outline-none"
                >
                    <svg
                        xmlns="http://www.w3.org/2000/svg"
                        class="h-6 w-6"
                        fill="none"
                        viewBox="0 0 24 24"
                        stroke="currentColor"
                    >
                        <path
                            stroke-linecap="round"
                            stroke-linejoin="round"
                            stroke-width="2"
                            d="M6 18L18 6M6 6l12 12"
                        />
                    </svg>
                </button>
            </div>
            
            <!-- Contenido del formulario -->
            <div class="p-6">
                <h2 class="text-xl font-bold mb-6 text-center text-primary">Iniciar sesión</h2>
                <form @submit.prevent="login">
                    <div class="mb-4">
                        <label for="email" class="block text-sm font-medium text-gray-700">Email</label>
                        <input
                            v-model="email"
                            type="email"
                            id="email"
                            class="mt-1 block w-full px-3 py-2 border text-gray-700 border-gray-300 rounded-md shadow-sm 
                                focus:outline-none focus:ring-tertiary focus:border-tertiary"
                            required
                        />
                    </div>
                    <div class="mb-4">
                        <label for="password" class="block text-sm font-medium text-gray-700">Contraseña</label>
                        <input
                            v-model="password"
                            type="password"
                            id="password"
                            class="mt-1 block w-full px-3 py-2 border text-gray-700 border-gray-300 rounded-md shadow-sm 
                                focus:outline-none focus:ring-tertiary focus:border-tertiary"
                            required
                        />
                    </div>
                    <!-- Botón de inicio de sesión -->
                    <button
                        type="submit"
                        class="w-full bg-primary text-white py-2 px-4 rounded-md hover:bg-tertiary focus:outline-none focus:ring-2 focus:ring-tertiary"
                    >
                        Iniciar Sesión
                    </button>
                    <!-- Recuperar contraseña -->
                    <div class="absolute mt-3 pr-2 right-4">
                        <a 
                            href="#" 
                            class="text-gray-700 text-sm hover:text-tertiary"
                            @click.prevent="openPasswordRecoveryForm"
                        >
                            ¿Problemas con tu contraseña?
                        </a>
                    </div>
                    <!-- Botón de registro -->
                    <button
                        type="button"
                        @click="openRegisterForm"
                        class="w-full bg-white border-2 border-primary text-primary py-2 px-4 rounded-md mt-16
                            hover:bg-primary hover:text-white focus:outline-none focus:ring-2 focus:ring-primary"
                    >
                        ¿Aún sin cuenta? Regístrate
                    </button>
                </form>
                <p v-if="message" class="mt-4 text-center text-sm" :class="{'text-secondary': success, 'text-primary': !success}">
                    {{ message }}
                </p>
            </div>
        </div>
    </div>
</template>