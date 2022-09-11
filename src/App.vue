<template>
  <v-app>
    <div class="container">
      <AddTodo/>
      <FilterTodos/>
      <Todos/>
    </div>
    <v-main>
      <router-view/>
    </v-main>
  </v-app>
</template>

<script>
import AddTodo from './components/AddTodo.vue'
import Todos from './components/Todos.vue';
import FilterTodos from './components/FilterTodos.vue';

export default {
    name: "App",
    data: () => ({
    //
    }),
    components: { Todos, AddTodo, FilterTodos }
};
</script>
<style scoped>
body{
  font-family: 'Franklin Gothic Medium', 'Arial Narrow', Aria sans-serif;
  line-height: 1.6;
  background-color: #e8f7f0;
}
.container{
  width: 70%;
  margin: auto;
  overflow: auto;
   margin-top: 20px;
  padding: 5px 2rem
}
</style>
