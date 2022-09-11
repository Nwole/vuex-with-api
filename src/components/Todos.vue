<template>
  <div>
    <h3>Todos</h3>
    <div class="todos  ">
        <div v-for="todo in allTodos" :key="todo.id" class="todo">
            <h3>{{todo.title}}</h3>
            <v-icon style="color:red" @click="deletetodo(todo.id)" >mdi-delete</v-icon>
        </div>
    </div>
  </div>
</template>

<script>
import { mapGetters, mapActions } from 'vuex';
export default {
name: 'Todos',
methods: {
...mapActions(['fetchTodos', 'deletetodo'])
},
computed: mapGetters(['allTodos']),
created(){
    this.fetchTodos()
}
}
</script>

<style>
.todos{
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    grid-gap: 1rem
}
.todo{
    border: 1px solid #ccc;
    background-color: #41b883;
    padding: 1rem;
    border-radius: 5px;
    text-align: center;
    position: relative;
    cursor: pointer;
    display: flex;
    align-items: center;
    justify-content: space-between;
    gap: 20px;
}
.todo:hover {
  background-color: yellow;
}
.delete-icon{
    position: absolute;
    bottom: 10px;
    right: 10px;
    color: #fff;
    cursor: pointer;
}
@media(max-width: 500px){
    .todos{
        grid-template-columns: 1fr;
    }
}
</style>