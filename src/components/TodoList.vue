<template>
    <Title />
    <form id="Form" @submit.prevent>

        <input id="lista" v-model="lista" type="text">
        
        <button type="submit" @click="addToDoList">Agregar</button>

    </form>

    <br><br>

    <div v-for="(item, index) in todo_list" :key="item.id">
        
        {{index + 1}} - {{item}}

    </div>
</template>

<script>

import Title from './Title.vue'

export default {
    name: 'TodoList',
    components: {
        Title,
    },
    data () {
        return {
            lista: "",
            todo_list: [],
        }
    },
    methods: {
        preventForm(){
            const form = document.querySelector('#Form');
            form.preventDefault();
        },
        funciona() {
            console.log(this.lista)
        },

        addToDoList(){
            const addLista = document.querySelector('#lista');
            if(addLista.value !== ""){
                this.todo_list.push(this.lista)
            }else
                console.log("No has agregado lista")
        }
    }
}
</script>

<style>

</style>