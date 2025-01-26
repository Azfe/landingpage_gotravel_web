<script setup>
import CardRecomendation from './CardRecomendation.vue';

</script>

<template>
    <div class="p-6" id="our_recomendations">
            <h2 class="text-3xl font-semibold text-primary">Recomendaciones</h2>
            <div class="w-auto h-72 items-center mt-6 overflow-x-auto overscroll-x-contain flex space-x-4 lg:space-x-6 overflow-y-hidden">
                <!-- Cards -->
                <div class="Card">
                    <div class="w-full h-3/5 rounded-t-lg bg-norway bg-cover"></div>
                    <div class="w-full h-2/5 bg-secondary rounded-b-lg">
                        <p class="text-white text-bold text-xl px-4 py-2">Noruega</p>
                        <p class="text-white text-md px-4">Paisajes increibles</p>
                    </div>
                </div>
                <div class="Card">
                    <div class="w-full h-3/5 rounded-t-lg bg-new_york bg-cover"></div>
                    <div class="w-full h-2/5 bg-white rounded-b-lg ">
                        <p class="text-tertiary text-bold text-xl px-4 py-2">Nueva York</p>
                        <p class="text-tertiary text-md px-4">La ciudad que nunca duerme</p>
                    </div>
                </div>
                <div class="Card">
                    <div class="w-full h-3/5 rounded-t-lg bg-yosemite bg-cover"></div>
                    <div class="w-full h-2/5 bg-secondary rounded-b-lg">
                        <p class="text-white text-bold text-xl px-4 py-2">Yosemite</p>
                        <p class="text-white text-md px-4">Un descanso del mundo</p>
                    </div>
                </div>
                <div class="Card">
                    <div class="w-full h-3/5 rounded-t-lg bg-seattle bg-cover"></div>
                    <div class="w-full h-2/5 bg-white rounded-b-lg">
                        <p class="text-tertiary text-bold text-xl px-4 py-2">Seattle</p>
                        <p class="text-tertiary text-md px-4">La ciudad esmeralda</p>
                    </div>
                </div>
            </div>
    </div>
</template>

<style>

</style>