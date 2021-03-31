<template>
<div>
    <h1>Crear una nueva tarea</h1>
    <form>
        <label for="tarea">Tarea:</label>
        <input type="text" v-model="nuevaTarea" id="tarea" placeholder="Ingresa nueva tarea">
        <button type="button" @click="crearTarea">Agregar tarea</button>
    </form>

    <h2>Lista</h2>
    <div class="lista">
    <ol>
        <li v-for="(tarea, i) in tareas" :key="'tarea' + i"> {{tarea.text}} </li>
    </ol>
    </div>

</div>
</template>

<script>
export default {
    data: () => ({
        nuevaTarea: "",
        tareas: []
    }),
    methods: {
        crearTarea(){
            let tarea = {
                text: this.nuevaTarea
            };
            this.tareas.push(tarea);
            this.nuevaTarea = "";
            console.log(this.tareas);
        }
    }
};
</script>

<style scoped>
ol{
    margin: 1.875rem auto;
}
li{
    margin-top: 1.875rem;
}
.lista{
    text-align: center;
}
</style>