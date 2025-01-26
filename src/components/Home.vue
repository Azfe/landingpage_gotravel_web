<script setup>

</script>

<template>
    <div id="home">
            <div class="w-full h-3/4">
                <div class="w-full h-full flex flex-col absolute space-y-96 py-4 items-center lg:space-y-0 lg:items-start lg:justify-start lg:pt-[11rem]">
                    <input class="lg:hidden p-3 outline-none rounded-full shadow-lg transition duration-300 focus-within:shadow-sm focus:outline-none focus:ring-2  focus:w-11/12"
                        placeholder="San Francisco" type="search">
                    <div class=" hidden h-auto lg:w-2/5 lg:flex pb-6 ">
                        <p class=" lg:flex text-4xl ml-8 font-bold text-primary">Encuentra más ubicaciones como esta</p>
                    </div>
                    <button class="w-48 h-auto p-3 lg:ml-8 rounded-full text-lg font-semibold bg-white text-primary shadow-md
                    transition-all duration-500 ease-in-out hover:bg-primary hover:text-white transform hover:-translate-y-1 hover:scale-110" id='explore-more'>
                        Explorar
                    </button>
                </div>
                <div class="w-full h-full bg-cover lg:h-[36rem] lg:bg-cover bg-sanFranciscoDesktop lg:bg-center">
                    <img class="w-full h-full lg:hidden" src="../assets/images/sanFrancisco.jpg" alt="San Francisco">
                </div>                
            </div>
        </div>
</template>

<style></style>