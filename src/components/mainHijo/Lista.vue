<template>
    <div class="container">
        <div class="row">
            <div class="col-12">
                <input type="text" v-model="tarea" placeholder="Agregar nueva tarea">
                <button @click="mostrarTarea">INGRESAR</button>
                <div v-show="listaTareas.length > 0" class="mt-5 bg-light text-left">
                <p class="border border-top">Total Tareas: {{listaTareas.length}}</p>
                    <ul class="boton">
                        <li v-for="(tarea,index) in listaTareas" :key="index">{{index+1}} - {{tarea}} 
                            <button type="button" class="btn btn-danger btn-sm" @click="eliminarTarea(index)">Eliminar Tarea</button>
                        </li>
                    </ul>
                </div>
               
            </div>
        </div>
    </div>
</template>

<script>
    export default {
        name:'Lista',
        data(){
            return {
                tarea:'',
                listaTareas:[]
            }
        },
        methods: {
            mostrarTarea(){
                if (this.tarea) {
                this.listaTareas.push(this.tarea);
                this.tarea = "";
            } else {
                console.log("no hay nueva tarea");
            }
            },
            eliminarTarea(){
                this.listaTareas.splice(index,1);
            }
        }

    }
</script>

<style>

</style>