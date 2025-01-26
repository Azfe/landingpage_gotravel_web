<script setup>
    import { ref } from 'vue';

    // Estados reactivos
    const email = ref('');
    const message = ref('');
    const success = ref(false);
    const isVisible = ref(false);

    // Método para recuperar la contraseña
    const recoverPassword = async () => {
    try {
        message.value = 'Se ha enviado un correo para recuperar tu contraseña.';
        success.value = true;
    } catch (error) {
        message.value = 'Error al intentar recuperar la contraseña.';
        success.value = false;
    }
    };

    // Método para abrir el formulario
    const openForm = () => {
    isVisible.value = true;
    };

    // Método para cerrar el formulario
    const closeForm = () => {
    isVisible.value = false;
    email.value = '';
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
        class="fixed inset-0  flex justify-end transition-opacity duration-300"
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
                <h2 class="text-xl font-bold mb-6 text-center text-primary">Recuperar Contraseña</h2>
                <form @submit.prevent="recoverPassword">
                    <div class="mb-4">
                        <label for="email" class="block text-sm font-medium text-gray-700">Email</label>
                        <input
                            v-model="email"
                            type="email"
                            id="email"
                            class="mt-1 block w-full px-3 py-2 border text-gray-700 border-gray-300 rounded-md shadow-sm focus:outline-none focus:ring-tertiary focus:border-tertiary"
                            required
                        />
                    </div>
                    <button
                        type="submit"
                        class="w-full bg-primary text-white py-2 px-4 rounded-md hover:bg-tertiary focus:outline-none focus:ring-2 focus:ring-tertiary"
                    >
                        Recuperar Contraseña
                    </button>
                </form>
                <p v-if="message" class="mt-4 text-center text-sm" :class="{'text-secondary': success, 'text-primary': !success}">
                    {{ message }}
                </p>
            </div>
        </div>
    </div>
</template>