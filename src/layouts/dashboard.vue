<template>
    <div class="block h-full w-full overflow-hidden">

        <nav class="flex justify-between bg-teal-700 w-full py-3 px-5 text-white">

            <img class="h-8" src="../assets/logo.png" />

            <div class="lg:hidden">
                <img class="h-6" src="../assets/zondicons/menu.svg" @click="mostrar" id="menu" />
                <img class="hidden h-6" src="../assets/zondicons/close.svg" @click="ocultar" id="close" />
            </div>

            <div class="hidden lg:block text-white" >
                <a class="text-white text-decoration:none px-2">Opción 1</a>
                <a class="text-white text-decoration:none px-2">Opción 2</a>
                <a class="text-white text-decoration:none px-2">Opción 3</a>
                <a class="text-white text-decoration:none px-2">Opción 4</a>
            </div>

        </nav>

        <div class="flex relative h-full overflow-hidden">

            <div class="hidden absolute w-full h-full lg:hidden" id='mask' @click="ocultar"></div>

            <div class="hidden w-3/4 md:w-1/4 lg:block lg:w-2/12 xl:1/12 py-3 px-5 bg-teal-700 text-white" id="sidebar">
                <div class="" >
            
                    <button class=" w-full h-full border border-white rounded text-center " arget="titulo" @click="dropshow">
                        Titulo
                    </button>
                    
                    <div class="hidden" id="titulo" >
                        <p>Opción 1</p>
                        <p>Opción 2</p>
                        <p>Opción 3</p>
                    </div>
                </div>
            </div>

            <div class="w-full lg:w-10/12 xl:11/12 py-3 px-5 bg-gray-100" >
                <h1>Hola</h1>
            </div>

        </div>

    </div>
</template>

<script>
export default {
    data: function () {
         return {

         }
    },
    methods:{
        mostrar() {
            let sidebar = document.getElementById('sidebar')
            sidebar.classList.remove('hidden')
            sidebar.classList.add('block')
            sidebar.classList.add('mini_menu')
    
            let mask = document.getElementById('mask')
            mask.classList.remove('hidden')
            mask.classList.add('block')

            document.getElementById('close').classList.remove('hidden')
            document.getElementById('menu').classList.add('hidden')
        },
        ocultar() {
            let mask = document.getElementById('mask')
            mask.classList.remove('block')
            mask.classList.add('hidden')

            let sidebar = document.getElementById('sidebar')
            sidebar.classList.add('hidden')
            sidebar.classList.remove('block')
            sidebar.classList.remove('mini_menu')

            document.getElementById('menu').classList.remove('hidden')
            document.getElementById('close').classList.add('hidden')
        },
        dropshow(e) {
            console.log(e.target)
        }
    }

}
</script>

<style>
    #mask {
        background-color: rgba(0, 0, 0, 0.5);
    }
    .mini_menu {
        position: absolute;
        height: 100%;
    }
</style>