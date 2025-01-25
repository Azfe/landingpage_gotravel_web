<script setup>
</script>

<template>
    <!--trending_stays-->
    <div class="px-4 w-full h-auto" id="trending_stays">
        <!-- grid imgs -->
        <h2 class="text-3xl text-primary font-semibold pb-6 mt-6">Alojamientos</h2>
        <div class="w-full h-full flex flex-col space-y-4 items-center justify-center">
            <div class="w-full h-96 bg-chicago bg-cover bg-center rounded-2xl lg:h-[38rem] lg:bg-center">
                <div class="lg:ml-40">
                    <p class="CardTitle">Chicago</p>
                    <p class="text-md pl-8 text-white mr-12 lg:text-base">2 habitaciones, 1 baño y cocina</p>
                </div>                    
            </div>
            
            <div class="w-full h-full grid grid-cols-1 lg:grid-cols-5 lg:grid-rows-2 lg:place-items-center lg:place-content-stretch gap-4">
                <div class="w-full h-96 bg-LA bg-cover bg-center rounded-2xl lg:row-span-2 lg:col-span-2 lg:h-[49rem] lg:bg-center">
                    <p class="CardTitle">Los Ángeles</p>
                    <p class="text-md pl-8 text-white mr-12 lg:mr-8 lg:text-base">4 habitaciones, 3 baños, cocina y piscina privada</p>
                </div>                    
                <div class="w-full h-96 bg-miami bg-cover bg-center rounded-2xl lg:row-span-1 lg:col-span-3 lg:bg-center">
                    <p class="CardTitle">Miami</p>
                    <p class="text-md pl-8 text-white mr-12 lg:text-base">3 habitaciones, 2 baños, cocina e increibles vistas al mar</p>
                </div>
                <div class="w-full h-96 bg-bali bg-cover bg-center rounded-2xl lg:row-span-1 lg:col-span-3 lg:bg-center">
                    <p class="CardTitle">Bali</p>
                    <p class="text-md pl-8 text-white mr-12 lg:text-base">2 habitaciones, 2 baños, cocina y piscina privada</p>
                </div>                        
            </div>                
        </div>
    </div>
    
</template>